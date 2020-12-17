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
ms.assetid: 3C261AFA-57EC-4BEA-A9A5-0499B76C3846
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Enable-MbamWebApplication
ms.reviewer:
---

# Enable-MbamWebApplication

## SYNOPSIS
Enables a web application.

## SYNTAX

### ParameterSetAdministrationPortal
```
Enable-MbamWebApplication [-SkipValidation] [-ComplianceAndAuditDBConnectionString <String>]
 [-RecoveryDBConnectionString <String>] -AdvancedHelpdeskAccessGroup <String> -HelpdeskAccessGroup <String>
 -ReportsReadOnlyAccessGroup <String> [-Certificate <X509Certificate2>] [-HostName <String>] [-Port <Int32>]
 -ReportUrl <Uri> [-VirtualDirectory <String>] [-InstallationPath <String>]
 [-WebServiceApplicationPoolCredential <PSCredential>] [-CMIntegrationMode] [-AdministrationPortal] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ParameterSetSelfServicePortal
```
Enable-MbamWebApplication [-SkipValidation] [-ComplianceAndAuditDBConnectionString <String>]
 [-RecoveryDBConnectionString <String>] [-Certificate <X509Certificate2>] [-HostName <String>] [-Port <Int32>]
 [-VirtualDirectory <String>] [-InstallationPath <String>]
 [-WebServiceApplicationPoolCredential <PSCredential>] [-CompanyName <String>] [-HelpdeskUrlText <String>]
 [-HelpdeskUrl <Uri>] [-DisableNoticePage] [-NoticeTextPath <String>] [-SelfServicePortal] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ParameterSetAgentService
```
Enable-MbamWebApplication [-SkipValidation] [-ComplianceAndAuditDBConnectionString <String>]
 [-RecoveryDBConnectionString <String>] [-Certificate <X509Certificate2>] [-HostName <String>] [-Port <Int32>]
 [-InstallationPath <String>] [-WebServiceApplicationPoolCredential <PSCredential>] [-CMIntegrationMode]
 [-TpmLockoutAutoReset] [-DataMigrationAccessGroup <String>] [-AgentService] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-MbamWebApplication** cmdlet enables a Microsoft BitLocker Administration and Monitoring (MBAM) web application on the local server.
The cmdlet enables one of the following web applications: 

- Administration and Monitoring Website
- Agent Services
- Self-Service Portal

## EXAMPLES

### Example 1: Enable Administration and Monitoring Website
```
PS C:\> Enable-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Compliance Status" -RecoveryDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Recovery and Hardware" -AdvancedHelpdeskAccessGroup "Contoso\AdvancedUserGroup" -HelpdeskAccessGroup "Contoso\StandardUserGroup" -ReportsReadOnlyAccessGroup "Contoso\ReportUserGroup" -ReportUrl "https://ContosoReportsServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalComputer\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

This command enables the Administration and Monitoring Website web application on the current server.
The portal uses the Compliance and Audit Database and the Recovery Database on ContosoDatabaseServer, and it uses the reports on ContosoReportsServer.

### Example 2: Enable Self-Service Portal
```
PS C:\> Enable-MbamWebApplication -SelfServicePortal -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Compliance Status" -RecoveryDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Recovery and Hardware" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalComputer\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

This command enables the Self-Service Portal web application on the current server.
The Self-Service Portal uses the Compliance and Audit Database and the Recovery Database on ContosoDatabaseServer.

### Example 3: Enable Agent Services
```
PS C:\> Enable-MbamWebApplication -AgentService -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Compliance Status" -RecoveryDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Recovery and Hardware" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalComputer\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

This command enables the Agent Services feature on the current server.
The services use the Compliance and Audit Database and the Recovery Database on ContosoDatabaseServer.

### Example 4: Enable Administration and Monitoring Website for a mirrored environment
```
PS C:\> Enable-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Failover Partner=ContosoMirror;Initial Catalog=MBAM Compliance Status" -RecoveryDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Failover Partner=ContosoMirror;Initial Catalog=MBAM Recovery and Hardware" -AdvancedHelpdeskAccessGroup "Contoso\AdvancedUserGroup" -HelpdeskAccessGroup "Contoso\StandardUserGroup" -ReportsReadOnlyAccessGroup "Contoso\ReportUserGroup" -ReportUrl "https://ContosoReportsServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalComputer\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

This command enables the Administration and Monitoring Website web application, and it configures web applications to use a mirrored Microsoft SQL Server environment.
The connection strings specify a failover partner.

### Example 5: Enable the Self-Service Portal for a mirrored environment
```
PS C:\> Enable-MbamWebApplication -SelfServicePortal -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Failover Partner=ContosoMirror;Initial Catalog=MBAM Compliance Status" -RecoveryDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Failover Partner=ContosoMirror;Initial Catalog=MBAM Recovery and Hardware" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalComputer\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

This command enables the Self-Service Portal on the current server, and it configures web applications to use a mirrored SQL Server environment.
The connection strings specify a failover partner.

## PARAMETERS

### -AdministrationPortal
Indicates that this cmdlet acts on the Administration and Monitoring Website web application.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetAdministrationPortal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdvancedHelpdeskAccessGroup
Specifies a domain user group.
This group has permissions for all areas of the Administration and Monitoring Website web application, except for reports.

```yaml
Type: String
Parameter Sets: ParameterSetAdministrationPortal
Aliases: AdvancedHelpdeskGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AgentService
Indicates that this cmdlet acts on the Agent Services web application.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetAgentService
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CMIntegrationMode
Indicates that all reports, except the Recovery Audit Report, are integrated into Microsoft Endpoint Configuration Manager.
If you enable the Configuration Manager Integration feature, specify this parameter.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetAdministrationPortal
Aliases: CMMode

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetAgentService
Aliases: CMMode

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificate
Specifies the certificate to use for encrypted web communications.
If you do not specify a certificate, web communications are not encrypted.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -CompanyName
Specifies the company name associated with the web application.

```yaml
Type: String
Parameter Sets: ParameterSetSelfServicePortal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComplianceAndAuditDBConnectionString
Specifies a connection string.
The web application uses the string that this parameter specifies to connect to the Compliance and Audit Database feature.
The connection string must contain values for the **Integrated Security** and **Initial Catalog** fields.

If you do not specify this parameter, the cmdlet uses the connection string that you previously specified for any enabled web application.
All of the web applications connect to the Compliance and Audit Database by using the same connection string.
If you specify connection strings more than once, web applications will use the most recent value.

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

### -DataMigrationAccessGroup
Specifies the domain user group that is authorized to migrate Recovery information to MBAM server.

```yaml
Type: String
Parameter Sets: ParameterSetAgentService
Aliases: DataMigrationGroup

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisableNoticePage
Indicates the Self-Service Portal notice text on or off. By default, the notice text is turned on.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetSelfServicePortal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HelpdeskAccessGroup
Specifies the domain user group that has permissions for the Manage TPM and Drive Recovery areas of the Administration and Monitoring Website web application.

```yaml
Type: String
Parameter Sets: ParameterSetAdministrationPortal
Aliases: HelpdeskGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HelpdeskUrl
Specifies the URL for the MBAM help desk site.

```yaml
Type: Uri
Parameter Sets: ParameterSetSelfServicePortal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HelpdeskUrlText
Specifies the helpdesk link text that will be displayed on the self-service portal.

```yaml
Type: String
Parameter Sets: ParameterSetSelfServicePortal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostName
Specifies a host name.
If you do not specify a host name, the cmdlet uses the fully qualified host name of the local computer.
Ensure that you specify the same host name for all of the web applications.

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

### -InstallationPath
Specifies the installation path of the web application.
The installation process creates a folder named Microsoft BitLocker Management Solution in location that this parameter specifies.
If you do not specify a path, the cmdlet uses \<IIS inetpub path\>.
Specify the same installation path for all of the web applications.

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

### -NoticeTextPath
Specifies the absolute path to the text file (.txt) that contains the notice text.

```yaml
Type: String
Parameter Sets: ParameterSetSelfServicePortal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
Specifies the web service port.
If you do not specify a port, unencrypted communications use port 80, and encrypted communications use port 443.
You need to specify the same value for all of the web applications.

You must configure your firewall to allow communication through the ports for the Self-Service Portal and the Administration and Monitoring Website web applications.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecoveryDBConnectionString
Specifies a connection string.
The web application uses the string that this parameter specifies to connect to the Recovery Database.
The connection string must contain values for the **Integrated Security** and **Initial Catalog** fields.

If you do not specify this parameter, the cmdlet uses the connection string that you previously specified for any enabled web application.
All of the web applications connect to the Recovery Database by using the same connection string.
If you specify connection strings more than once, web applications use the most recent value.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RecoveryDB

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportUrl
Specifies the URL for the reports that the Microsoft SQL Server Reporting Services instance publishes.

```yaml
Type: Uri
Parameter Sets: ParameterSetAdministrationPortal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReportsReadOnlyAccessGroup
Specifies a domain user group.
Specify a group that has read permissions for the Reports area of the Administration and Monitoring Website web application.
The value for this parameter must be the same as the group that you specify for the *ReportsReadOnlyAccessGroup* parameter in the **Enable-MbamReport** cmdlet.

```yaml
Type: String
Parameter Sets: ParameterSetAdministrationPortal
Aliases: ReportsGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SelfServicePortal
Indicates that this cmdlet acts on the Self-Service Portal web application.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetSelfServicePortal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -TpmLockoutAutoReset
Indicates that Agent Services allows TPM lockout resets.

```yaml
Type: SwitchParameter
Parameter Sets: ParameterSetAgentService
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDirectory
Specifies a virtual directory for the web application.
If you do not specify a virtual directory, the cmdlet uses the value HelpDesk for the Administration and Monitoring Website, or it uses the value self-service for the Self-Service Portal.

```yaml
Type: String
Parameter Sets: ParameterSetAdministrationPortal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ParameterSetSelfServicePortal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WebServiceApplicationPoolCredential
Specifies the domain user that the application pool for the web applications uses.
If you specified a domain user group for the *AccessAccount* parameter when you ran the **Enable-MbamDatabase** cmdlet, the domain user that you specify for this parameter must be a member of that group.

If you do not specify this parameter, the cmdlet uses the credentials that you previously specified for any enabled web application.
All of the web applications use the same application pool credentials.
If you specify credentials for web applications more than once, web applications use the most recent value.

Important: For improved security, use an account that has limited user rights.
Also, configure the account so that the password never expires.
Verify that the account that you specify for this parameter is a built-in IIS_IUSRS account or has been added to the Impersonate a client after authentication and Log on as a batch job local security settings.
To view the local security setting, open the Local Security Policy editor, expand the Local Policies node, click the User Rights Assignment node, and then double-click the Impersonate a client after authentication and Log on as a batch job policies in the right pane.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: AppPoolCred

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

[Disable-MbamWebApplication](disable-mbamwebapplication.md)

[Get-MbamWebApplication](get-mbamwebapplication.md)

[Test-MbamWebApplication](test-mbamwebapplication.md)

[Enable-MbamReport](enable-mbamreport.md)

[Enable-MbamDatabase](enable-mbamdatabase.md)


