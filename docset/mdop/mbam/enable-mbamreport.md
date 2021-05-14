---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Enable-MbamReport
---

# Enable-MbamReport

## SYNOPSIS
Enables the Reports feature on the local server.

## SYNTAX

```
Enable-MbamReport [-SkipValidation] [-ComplianceAndAuditDBConnectionString <String>]
 -ComplianceAndAuditDBCredential <PSCredential> [-SsrsInstance <String>] -ReportsReadOnlyAccessGroup <String>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MbamReport** cmdlet enables the Microsoft BitLocker Administration and Monitoring (MBAM) Reports feature on a local Microsoft SQL Server Reporting Services instance.

## EXAMPLES

### Example 1: Enable the Reports feature
```
PS C:\> Enable-MbamReport -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Compliance Status" -ComplianceAndAuditDBCredential (Get-Credential) -ReportsReadOnlyAccessGroup "Contoso\ReportsGroup"
```

This command enables the Reports feature on the local server.
The feature uses the Compliance and Audit Database on ContosoDatabaseServer.
The command prompts you to enter credentials to access the Compliance and Audit Database.
The reports group is Contoso\ReportsGroup.
The command installs reports on the default SQL Server Reporting Services instance.

## PARAMETERS

### -ComplianceAndAuditDBConnectionString
Specifies a connection string.
The local SQL Server Reporting Services uses the string that this parameter specifies to connect to the Compliance and Audit Database feature.
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
The domain user in the credentials must be the same as the user that you specify for the *ReportAccount* parameter in the **Enable-MbamDatabase** cmdlet.
If you specified a domain user group for the *ReportAccount* parameter, the credentials that you specify for the current parameter must be a member of that group.

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

### -ReportsReadOnlyAccessGroup
Specifies a domain user group.
Specify a group that has read permission for the reports.

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

[Disable-MbamReport](disable-mbamreport.md)

[Get-MbamReport](get-mbamreport.md)

[Test-MbamReport](test-mbamreport.md)

[Enable-MbamDatabase](enable-mbamdatabase.md)


