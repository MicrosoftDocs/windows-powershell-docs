---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Get-MbamReport
---

# Get-MbamReport

## SYNOPSIS
Gets the configuration of the Reports feature.

## SYNTAX

```
Get-MbamReport [<CommonParameters>]
```

## DESCRIPTION
The **Get-MbamReport** cmdlet gets the configuration of the Microsoft BitLocker Administration and Monitoring (MBAM) Reports feature.

## EXAMPLES

### Example 1: Get configuration of the Reports feature
```
PS C:\> Get-MbamReport
Name                                 : Reports
Enabled                              : True
Description                          : This feature includes reports for the Compliance and Auditing data that has been gathered by the MBAM Client.
ComplianceAndAuditDBConnectionString : Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog="MBAM Compliance Status";
ComplianceAndAuditDBUser             : ContosoDomain\ReportAccount
SsrsInstance                         : MSSQLSERVER
ReportsReadOnlyAccessGroup           : ContosoDomain\ReportGroup
ReportUrl                            : https://ContosoReportsServer:443/ReportServer/ReportService2005.asmx
```

Gets the configuration of the Reports feature on the local server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.MBAM.Server.Commands.ReportConfiguration

## NOTES

## RELATED LINKS

[Disable-MbamReport](disable-mbamreport.md)

[Enable-MbamReport](enable-mbamreport.md)

[Test-MbamReport](test-mbamreport.md)


