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
ms.assetid: FAB50B88-10A7-42DE-8D28-9C90F3C4072C
ms.date: 12/05/2016
ms.devlang: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-MbamWebApplication
ms.reviewer:
---

# Get-MbamWebApplication

## SYNOPSIS
Gets the configuration of a web application.

## SYNTAX

### ParameterSetAdministrationPortal
```
Get-MbamWebApplication [-AdministrationPortal] [<CommonParameters>]
```

### ParameterSetAgentService
```
Get-MbamWebApplication [-AgentService] [<CommonParameters>]
```

### ParameterSetSelfServicePortal
```
Get-MbamWebApplication [-SelfServicePortal] [<CommonParameters>]
```

## DESCRIPTION
The **Get-MbamWebApplication** cmdlet gets the configuration of a Microsoft BitLocker Administration and Monitoring (MBAM) web application.

## EXAMPLES

### Example 1: Get the configuration of Administration and Monitoring Website
```
PS C:\> Get-MbamWebApplication -AdministrationPortal
Name                                 : Administration Web Portal
Enabled                              : True
Description                          : This feature includes the Help Desk web application for administration.
InstallationPath                     : C:\inetpub
HostName                             : MYSERVER.contoso.com
Port                                 : 443
CertificateThumbprint                : E2A7EA5533890D6567E40DFC46F53B3D31D6B689
ComplianceAndAuditDBConnectionString : Integrated Security=SSPI;Data Source=MyDatabaseServer;Initial Catalog="MBAM Compliance Status";
RecoveryDBConnectionString           : Integrated Security=SSPI;Data Source=MyDatabaseServer;Initial Catalog="MBAM Recovery and Hardware";
WebServiceApplicationPoolUser        : MyDomain\MBAMWebServicesAccount
VirtualDirectory                     : /HelpDesk
CMIntegrationMode                    : False
ReportUrl                            : https://MyReportsServer/ReportServer
AdvancedHelpdeskAccessGroup          : MyDomain\AdvancedHelpdeskUserGroup
HelpdeskAccessGroup                  : MyDomain\HelpdeskUserGroup
ReportsReadOnlyAccessGroup           : MyDomain\ReportsUserGroup
```

This command gets the configuration of the Administration and Monitoring Website feature on the local server.

### Example 2: Get the configuration of the Self-Service Portal
```
PS C:\> Get-MbamWebApplication -SelfServicePortal
Name                                 : Self Service Web Portal
Enabled                              : True
Description                          : This feature includes the Self Service web application that allows users to recover their own BitLocker keys.
InstallationPath                     : C:\inetpub
HostName                             : MYSERVER.contoso.com
Port                                 : 443
CertificateThumbprint                : E2A7EA5533890D6567E40DFC46F53B3D31D6B689
ComplianceAndAuditDBConnectionString : Integrated Security=SSPI;Data Source=MyDatabaseServer;Initial Catalog="MBAM Compliance Status";
RecoveryDBConnectionString           : Integrated Security=SSPI;Data Source=MyDatabaseServer;Initial Catalog="MBAM Recovery and Hardware";
WebServiceApplicationPoolUser        : MyDomain\MBAMWebServicesAccount
VirtualDirectory                     : /SelfService
```

This command gets the configuration of the Self-Service Portal feature on the local server.

### Example 3: Get the configuration of the Agent Services feature
```
PS C:\> Get-MbamWebApplication -AgentService
Name                                 : Agent Web Services
Enabled                              : True
Description                          : This feature includes the web services to support the MBAM agent.
InstallationPath                     : C:\inetpub
HostName                             : MYSERVER.contoso.com
Port                                 : 443
ComplianceAndAuditDBConnectionString : Integrated Security=SSPI;Data Source=MyDatabaseServer;Initial Catalog="MBAM Compliance Status";
RecoveryDBConnectionString           : Integrated Security=SSPI;Data Source=MyDatabaseServer;Initial Catalog="MBAM Recovery and Hardware";
WebServiceApplicationPoolUser        : MyDomain\MBAMWebServicesAccount
CMIntegrationMode                    : False
```

This command gets the configuration of the Agent Services feature on the local server.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.MBAM.Server.Commands.AdministrationPortalConfiguration, Microsoft.MBAM.Server.Commands.SelfServicePortalConfiguration, Microsoft.MBAM.Server.Commands.AgentServiceConfiguration

## NOTES

## RELATED LINKS

[Disable-MbamWebApplication](disable-mbamwebapplication.md)

[Enable-MbamWebApplication](enable-mbamwebapplication.md)

[Test-MbamWebApplication](test-mbamwebapplication.md)


