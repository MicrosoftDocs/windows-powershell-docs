---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/get-rmsuserrequestreport?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RmsUserRequestReport
---

# Get-RmsUserRequestReport

## SYNOPSIS
Generates a user requests statistical report for the AD RMS cluster.

## SYNTAX

```
Get-RmsUserRequestReport [-StartTime <DateTime>] [-EndTime <DateTime>] [-UserName <String>]
 [-RequestType <String>] [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RmsUserRequestReport** cmdlet generates a report that contains statistics about the request activity of a single user on the Active Directory Rights Management Services (AD RMS) cluster.

To obtain the report, specify the *UserName* of the user for which you want a report and then set the *Path* parameter to the AD RMS provider drive path `<PSDrive>:\`Report where `<PSDrive>` is the provider drive ID.
You can also specify a relative path.
For example, a dot (.) specifies the current location.
This returns a UserId and applicable request types that you can then use with the cmdlet to produce a more detailed report.

The UserID value returned for a particular *UserName* is valid only for the cluster identified by the *Path* parameter specified when the UserID value was returned.
You cannot use the UserID to identify the same user in different clusters.

## EXAMPLES

### Example 1: Get a request report for a user
```
PS C:\> Get-RmsUserRequestReport -Path "." -UserName "CONTOSO\PFuller"
```

This command displays a summary report of the requests from the user PFuller of the Contoso domain.

### Example 2: Get an AcquireLicense request report for a user
```
PS C:\> Get-RmsUserRequestReport -Path "." -StartTime 2/1/2009 -EndTime 2/28/2009 -UserName "CONTOSO\PFuller" -RequestType "AcquireLicense"
```

This command displays the request by a specified user to acquire a license.

### Example 3: Get a user request report and display its information
```
PS C:\> Get-RmsUserRequestReport -Path "." -RequestType "AcquireLicense" -UserName "CONTOSO\PFuller" | Get-RmsRequestInfo -Path "."
```

This command displays detailed information about a user's request to acquire a license.
The **Get-RmsUserRequestReport** cmdlet retrieves the user's license request and then pipes the results to the **Get-RmsRequestInfo** cmdlet to display the details of the request.

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

### -EndTime
Specifies the end of a time period for a system health report.
This parameter specifies a time value.
See the description of the *StartTime* parameter for information on specifying a time.

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

### -RequestType
Specifies the type of user request, such as Acquire License, Pre-Certify, and Get Client Licensor Certificate.

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

`4/17/2006`

`Monday, April 17, 2006`

`2:22:45 PM`

`Monday, April 17, 2006 2:22:45 PM`

These examples specify the same date and the time without the seconds.

`4/17/2006 2:22 PM`

`Monday, April 17, 2006 2:22 PM`

`2:22 PM`

The following example shows how to specify a date and time by using the RFC1123 standard.
This example defines time by using Greenwich Mean Time (GMT).

`Mon, 17 Apr 2006 21:22:48 GMT`

The following example shows how to specify a round-trip value as Coordinated Universal Time (UTC).
This example represents Monday, April 17, 2006 at 2:22:48 PM UTC.

`2000-04-17T14:22:48.0000000`

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
Specifies the user for which you are requesting a user request report, in the format \<domain_name\>\\\<user_name\>.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Using Windows PowerShell with AD RMS](https://go.microsoft.com/fwlink/?LinkId=136806)

[Get-RmsCertChain](./Get-RmsCertChain.md)

[Get-RmsCertInfo](./Get-RmsCertInfo.md)

[Get-RmsRequestInfo](./Get-RmsRequestInfo.md)

