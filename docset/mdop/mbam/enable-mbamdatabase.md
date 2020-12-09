---
ms.technology: 
ms.mktglfcycl: manage
ms.author: v-kaunu
ms.prod: w10
ms.sitesec: library
author: Kateyanne
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro 
ms.assetid: 11E40BEC-7F27-48EE-9DF7-773CB5D45152
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Enable-MbamDatabase
ms.reviewer:
---

# Enable-MbamDatabase

## SYNOPSIS
Enables the Compliance and Audit and Recovery databases.

## SYNTAX

### ParameterSetCompliance
```
Enable-MbamDatabase [-SkipValidation] -ConnectionString <String> [-DatabaseName <String>]
 -AccessAccount <String> -ReportAccount <String> [-ComplianceAndAudit] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ParameterSetRecovery
```
Enable-MbamDatabase [-SkipValidation] -ConnectionString <String> [-DatabaseName <String>]
 -AccessAccount <String> [-Recovery] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MbamDatabase** cmdlet enables a Compliance and Audit or a Recovery Database.

## EXAMPLES

### Example 1: Enable the Compliance and Audit Database
```
PS C:\> Enable-MbamDatabase -ComplianceAndAudit -ConnectionString "Integrated Security=SSPI;Data Source=MyDatabaseServer" -AccessAccount "MyDomain\MyAccessAccount" -ReportAccount "MyDomain\MyReportAccount" -DatabaseName "MyComplianceDatabaseName"
```

This command enables the Compliance and Audit Database on MyDatabaseServer.
The name of the database is MyComplianceDatabaseName.
The domain account MyAccessAccount has read and write permission to the database, and MyReportAccount has read-only permission to the database for reporting purposes.
The current Windows account credentials are used for authentication.

### Example 2: Enable the Recovery Database
```
PS C:\> Enable-MbamDatabase -Recovery -ConnectionString "Integrated Security=SSPI;Data Source=MyDatabaseServer" -AccessAccount "MyDomain\MyAccessAccount" -DatabaseName "MyRecoveryDatabaseName"
```

This command enables the Recovery database on MyRecoveryDatabaseServer.
The name of the database is MyRecoveryDatabaseName.
The domain account MyAccessAccount has read/write permission to the database.
The command uses the current Windows account credentials for authentication.

## PARAMETERS

### -AccessAccount
Specifies a domain user or group.
This domain user or group has read and write permission to this database, which enables web applications to access the data and reports.
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
Indicates that the Compliance and Audit Database is enabled.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
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
If you do not specify a name, the Compliance and Audit Database is given the name MBAM Compliance Status, and the Recovery database is given the name MBAM Recovery and Hardware.

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

### -Recovery
Indicates that the Recovery Database is enabled.

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
This domain user or group has read-only permission to this database, which enables reports to access the compliance and audit data.
If the value is a domain user, the *ComplianceAndAuditDBCredential* parameter in the **Enable-MbamReport** cmdlet must use the same user account.
If the value is a domain user group, the domain account used by the *ComplianceAndAuditDBCredential* parameter must be a member of this group.

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

### -SkipValidation
Indicates that this cmdlet bypasses validation of parameter values.
If you specify this parameter, the feature may not function properly after you enable it.

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-MbamReport](enable-mbamreport.md)

[Enable-MbamWebApplication](enable-mbamwebapplication.md)

[Test-MbamDatabase](test-mbamdatabase.md)


