---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Test-MbamReport
---

# Test-MbamReport

## SYNOPSIS
Checks server prerequisites and validates parameter values for the Reports feature.

## SYNTAX

```
Test-MbamReport [-Detailed] [-ComplianceAndAuditDBConnectionString <String>]
 -ComplianceAndAuditDBCredential <PSCredential> [-SsrsInstance <String>] -ReportsReadOnlyAccessGroup <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **Test-MbamReport** cmdlet checks server prerequisites and validates parameter values for the Microsoft BitLocker Administration and Monitoring (MBAM) Reports feature.

## EXAMPLES

### Example 1: Check prerequisites and validate parameters for the Reports feature
```
PS C:\> Test-MbamReport -ComplianceAndAuditDBConnectionString "Data Source=MyDatabaseServer;Initial Catalog=MBAM Compliance Status;Integrated Security=True" -ReportsReadOnlyAccessGroup "MyDomain\MyReportsGroup"
True
```

This command checks the prerequisites and validates the parameters for the Reports feature on the local server.
The connection string specifies that ContosoDatabaseServer hosts the Compliance and Audit Database.
The cmdlet prompts you to enter credentials for the Compliance and Audit Database.
The reports group is ContosoDomain\ReportsGroup.

### Example 2: View details about prerequisites and validation for the Reports feature
```
PS C:\> Test-MbamReport -ComplianceAndAuditDBConnectionString "Data Source=MyDatabaseServer;Initial Catalog=MBAM Compliance Status;Integrated Security=True" -ReportsReadOnlyAccessGroup "MyDomain\MyReportsGroup" -Detailed
ID                  Type  Message
--                  ----  -------
ReportsInstallation Error Unable to connect to the Reporting Services web service. Error message: The request failed with HTTP status 504: Proxy Timeout (The connection timed out.).
False
```

This command displays detailed information about prerequisites and validation of parameters for the Reports feature.
This command specifies the *Detailed* parameter.

## PARAMETERS

### -ComplianceAndAuditDBConnectionString
Specifies a connection string.
The local Microsoft SQL Server Reporting Services uses the string that this parameter specifies to connect to the Compliance and Audit Database feature.
The connection string must contain values for the **Integrated Security** and **Initial Catalog** fields.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComplianceDB

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComplianceAndAuditDBCredential
Specifies the domain account credentials that the local SQL Server Reporting Services instance uses to connect to the Compliance and Audit Database.
The domain user in the credentials must be the same as or a member of the report account of the Compliance and Audit Database.

Important: For improved security, use an account that has limited privileges.
Also, configure the account so that the password never expires.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: ComplianceDBCred

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Detailed
Indicates that the cmdlet displays detailed information about the prerequisite check and parameter validation failures.

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

### -ReportsReadOnlyAccessGroup
Specifies a domain user group.
Specify a group that has read permissions for the reports.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ReportsGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SsrsInstance
Specifies the SQL Server Reporting Services instance.
After installation, this instance hosts the reports.
If you do not specify an instance, the cmdlet uses the default instance, MSSQLSERVER.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### bool

## NOTES

## RELATED LINKS

[Disable-MbamReport](disable-mbamreport.md)

[Enable-MbamReport](enable-mbamreport.md)

[Get-MbamReport](get-mbamreport.md)

[Microsoft BitLocker Administration and Monitoring](/microsoft-desktop-optimization-pack/mbam-v25/)
