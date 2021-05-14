---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Test-MbamDatabase
---

# Test-MbamDatabase

## SYNOPSIS
Checks server prerequisites and validates parameters for an MBAM database.

## SYNTAX

### ParameterSetCompliance
```
Test-MbamDatabase [-Detailed] -ConnectionString <String> [-DatabaseName <String>] -AccessAccount <String>
 -ReportAccount <String> [-ComplianceAndAudit] [<CommonParameters>]
```

### ParameterSetRecovery
```
Test-MbamDatabase [-Detailed] -ConnectionString <String> [-DatabaseName <String>] -AccessAccount <String>
 [-Recovery] [<CommonParameters>]
```

## DESCRIPTION
The **Test-MbamDatabase** cmdlet checks the server prerequisites and validates the parameters for the Microsoft BitLocker Administration and Monitoring (MBAM) database feature.

## EXAMPLES

### Example 1: Check prerequisites and validate parameters for the Compliance and Audit Database
```
PS C:\> Test-MbamDatabase -ComplianceAndAudit -ConnectionString "Integrated Security=SSPI;Data Source=MyDatabaseServer" -AccessAccount "MyDomain\MyAccessAccount" -ReportAccount "MyDomain\MyReportAccount" -DatabaseName "MyComplianceDatabaseName"
```

This command checks the prerequisites and validates the parameters to enable the Compliance and Audit Database on MyDatabaseServer.
The name of the database is MyComplianceDatabaseName.
The domain account MyAccessAccount has read/write permission to the database, and MyReportAccount has read-only permission to the database for reporting purposes.
The command uses the current Windows account credentials for authentication.

### Example 2: Check prerequisites and validate parameters for the Recovery Database
```
PS C:\> Test-MbamDatabase -Recovery -ConnectionString "Integrated Security=SSPI;Data Source=MyDatabaseServer" -AccessAccount "MyDomain\MyAccessAccount" -DatabaseName "MyRecoveryDatabaseName"
```

This command checks the prerequisites and validates the parameters to enable the Recovery Database on MyRecoveryDatabaseServer.
The name of the database is MyRecoveryDatabaseName.
The domain account MyAccessAccount has read/write permission to the database.
The command uses the current Windows account credentials for authentication.

### Example 3: Check prerequisites and validate parameters with detailed output
```
PS C:\> Test-MbamDatabase -ComplianceAndAudit -ConnectionString "Integrated Security=SSPI;Data Source=MyDatabaseServer" -AccessAccount "MyDomain\MyAccessAccount" -ReportAccount "MyDomain\MyReportAccount" -DatabaseName "MyComplianceDatabaseName" -Detailed


ID                              Type  Message
--                              ----  -------
ComplianceConnectionString      Error Cannot connect to the database with the provided connection string.
ComplianceDatabaseAccessAccount Error The user or group 'MyDomain\MyAccessAccount' cannot be found in Active Directory.
```

This command checks the prerequisites and validates the parameters to enable the Compliance and Audit Database on MyDatabaseServer with detailed output.

## PARAMETERS

### -AccessAccount
Specifies a domain user or group.
This domain user or group must have read/write permission to this database, which enables web applications to access the data and reports.
If the value is a domain user, the *WebServiceApplicationPoolCredential* parameter in the **Enable-MbamWebApplication** cmdlet must use the same user account.
If the value is a group, the domain account used by the *WebServiceApplicationPoolCredential* parameter must be a member of this group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComplianceAndAudit
Indicates that the cmdlet checks the server prerequisites and validates the parameter values for the Compliance and Audit Database.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetCompliance
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionString
Specifies the connection string used to connect to the data store.
The Integrated Security field must be in the connection string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database.
This parameter cannot contain leading or trailing spaces or non-printable characters.
If you do not specify a name, the Compliance and Audit Database is given the name MBAM Compliance Status, and the Recovery Database is given the name MBAM Recovery and Hardware.

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

### -Recovery
Indicates that the cmdlet checks the server prerequisites and validates the parameter values for the Recovery Database.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetRecovery
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReportAccount
Specifies a domain user or group.
This domain user or group must have read-only permission to this database, which enables reports to access the compliance and audit data.
If the value is a domain user, then the Compliance and Audit Database domain account of the report feature must be the same as the user.
If the value is a group, then the Compliance and Audit Database domain account of the report feature must be a member of this group.

```yaml
Type: String
Parameter Sets: ParameterSetCompliance
Aliases: 

Required: True
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

[Enable-MbamDatabase](enable-mbamdatabase.md)

[Enable-MbamWebApplication](enable-mbamwebapplication.md)

[Microsoft BitLocker Administration and Monitoring](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)


