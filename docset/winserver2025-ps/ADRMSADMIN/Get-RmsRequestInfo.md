---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.RightsManagementServices.Admin.dll-Help.xml
Module Name: ADRMSADMIN
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adrmsadmin/get-rmsrequestinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RmsRequestInfo
---

# Get-RmsRequestInfo

## SYNOPSIS
Generates a report about a particular user request for the AD RMS cluster.

## SYNTAX

```
Get-RmsRequestInfo -RequestId <Int64> [-Path] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RmsRequestInfo** cmdlet generates a report about a specified user request on the Active Directory Rights Management Services (AD RMS) cluster.

To obtain the report, specify the *RequestID* of the user request for which you want a report and then set the *Path* parameter to the AD RMS provider drive subpath `<PSDrive>:\`Report where `<PSDrive>` is the provider drive ID.
You can also specify a relative path.
For example, a dot (.) specifies the current location.

Use the **Get-RmsUserRequestReport** cmdlet to obtain the *RequestID* of the user request for which you want a detailed report.

## EXAMPLES

### Example 1: Get a specified user request
```
PS C:\> Get-RmsRequestInfo -Path "." -RequestID 1000
```

This command displays information about a particular user request.

### Example 2: Get a user request by type
```
PS C:\> Get-RmsUserRequestReport -Path "." -RequestType AcquireLicense -UserID 1 | Get-RmsRequestInfo -Path "."
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

### -Path
Specifies a provider drive and path or relative path on the current drive.
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

### -RequestId
Specifies the unique internal ID of a user request.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: True
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

[Get-RmsUserRequestReport](./Get-RmsUserRequestReport.md)

