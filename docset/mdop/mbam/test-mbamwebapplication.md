---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.MBAM.Server.Commands.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Test-MbamWebApplication
---

# Test-MbamWebApplication

## SYNOPSIS
Checks server prerequisites and validates parameter values for a web application feature.

## SYNTAX

### ParameterSetAdministrationPortal
```
Test-MbamWebApplication [-Detailed] [-ComplianceAndAuditDBConnectionString <String>]
 [-RecoveryDBConnectionString <String>] -AdvancedHelpdeskAccessGroup <String> -HelpdeskAccessGroup <String>
 -ReportsReadOnlyAccessGroup <String> [-Certificate <X509Certificate2>] [-HostName <String>] [-Port <Int32>]
 -ReportUrl <Uri> [-VirtualDirectory <String>] [-InstallationPath <String>]
 [-WebServiceApplicationPoolCredential <PSCredential>] [-CMIntegrationMode] [-AdministrationPortal]
 [<CommonParameters>]
```

### ParameterSetSelfServicePortal
```
Test-MbamWebApplication [-Detailed] [-ComplianceAndAuditDBConnectionString <String>]
 [-RecoveryDBConnectionString <String>] [-Certificate <X509Certificate2>] [-HostName <String>] [-Port <Int32>]
 [-VirtualDirectory <String>] [-InstallationPath <String>]
 [-WebServiceApplicationPoolCredential <PSCredential>] [-CompanyName <String>] [-HelpdeskUrlText <String>]
 [-HelpdeskUrl <Uri>] [-DisableNoticePage] [-NoticeTextPath <String>] [-SelfServicePortal] [<CommonParameters>]
```

### ParameterSetAgentService
```
Test-MbamWebApplication [-Detailed] [-ComplianceAndAuditDBConnectionString <String>]
 [-RecoveryDBConnectionString <String>] [-Certificate <X509Certificate2>] [-HostName <String>] [-Port <Int32>]
 [-InstallationPath <String>] [-WebServiceApplicationPoolCredential <PSCredential>] [-CMIntegrationMode]
 [-TpmLockoutAutoReset] [-DataMigrationAccessGroup <String>] [-AgentService] [<CommonParameters>]
```

## DESCRIPTION
The **Test-MbamWebApplication** cmdlet checks server prerequisites and validates parameter values for a Microsoft BitLocker Administration and Monitoring (MBAM) web application feature.
The cmdlet validates the current computer for one of the following web applications: 

- Administration and Monitoring Website
- Agent Services
- Self-Service Portal

## EXAMPLES

### Example 1: Check prerequisites and validate parameters for Administration and Monitoring Website
```
PS C:\> Test-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Compliance Status" -RecoveryDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Recovery and Hardware" -AdvancedHelpdeskAccessGroup "Contoso\AdvancedUserGroup" -HelpdeskAccessGroup "Contoso\StandardUserGroup" -ReportsReadOnlyAccessGroup "Contoso\ReportUserGroup" -ReportUrl "https://ContosoReportServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalComputer\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
True
```

This command checks the prerequisites and validates parameter values to enable the Administration and Monitoring Website web application on the current server.
The command tests a configuration of the website that uses the Compliance and Audit Database and the Recovery Database present in the ContosoDatabaseServer and the reports present in the ContosoReportsServer.

### Example 2: Check prerequisites and validate parameters for Self-Service Portal
```
PS C:\> Test-MbamWebApplication -SelfServicePortal -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Compliance Status" -RecoveryDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Recovery and Hardware" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalComputer\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689) 
True
```

This command checks the prerequisites and validates parameter values to enable the Self-Service Portal web application on this server.
The command checks the configuration of the Portal that uses the Compliance and Audit Database and the Recovery Database present in the ContosoDatabaseServer.

### Example 3: Check prerequisites and validate parameters for Agent Services
```
PS C:\> Test-MbamWebApplication -AgentService -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Compliance Status" -RecoveryDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Recovery and Hardware" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalComputer\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689) 
True
```

This command checks the prerequisites and validates parameter values to enable the Agent Services feature on the current server.
The cmdlets verify a configuration of services that uses the Compliance and Audit Database and the Recovery Database present in the ContosoDatabaseServer.

### Example 4: View detailed information
```
PS C:\> Test-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Compliance Status" -RecoveryDBConnectionString "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Recovery and Hardware" -AdvancedHelpdeskAccessGroup "Contoso\AdvancedUserGroup" -HelpdeskAccessGroup "Contoso\StandardUserGroup" -ReportsReadOnlyAccessGroup "Contoso\ReportUserGroup" -ReportUrl "https://ContosoReportServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalComputer\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689) -Detailed
Type    Message
----    -------
Error   Parameter "ComplianceAndAuditDBConnectionString" using value "Integrated Security=SSPI;Data Source=ContosoDatabaseServer;Initial Catalog=MBAM Compliance Status" is ...
Warning The application pool credential has a password that is set to expire.
Warning The application pool credential has administrator rights.
Warning Server communications have been configured without a certificate, which is not a secure configuration.
False
```

This command checks the prerequisites and validates parameter values to enable the Administration and Monitoring Website on this server.
The command specifies the *Detailed* parameter, and, therefore, displays detailed information.

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

All of the web applications connect to the Compliance and Audit Database by using the same connection string.

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

### -DisableNoticePage
Indicates whether the Self-Service Portal notice text is turned on or off. By default, the notice text is turned on.

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
The installation process creates a folder named Microsoft BitLocker Management Solution in the location that this parameter specifies.
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
You need to use the same connection string to ensure that all of the web applications connect to the Recovery Database.

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
You need to specify a group that has read permissions for the Reports area of the Administration and Monitoring Website web application.

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
If you do not specify a virtual directory, the cmdlet uses the value HelpDesk for Administration and Monitoring Website, or it uses the value SelfService for Self-Service Portal.

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

If you do not specify this parameter, the cmdlet uses the credentials that you previously specified for any enabled web application.
All of the web applications use the same application pool credentials.
If you specify credentials for web applications more than once, web applications use the most recent value.

Important: For improved security use an account that has limited user rights.
Also, you need to configure the account so that the password never expires.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### bool

## NOTES

## RELATED LINKS

[Disable-MbamWebApplication](disable-mbamwebapplication.md)

[Enable-MbamWebApplication](enable-mbamwebapplication.md)

[Get-MbamWebApplication](get-mbamwebapplication.md)

[Microsoft BitLocker Administration and Monitoring](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)


