---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: ADCSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsdeployment/uninstall-adcsenrollmentwebservice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-AdcsEnrollmentWebService
---

# Uninstall-AdcsEnrollmentWebService

## SYNOPSIS
Uninstalls the Certificate Enrollment Web service or individual instances of it.

## SYNTAX

### UninstallSingleInstance (Default)

```
Uninstall-AdcsEnrollmentWebService -CAConfig <String> -AuthenticationType <AuthenticationType>
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UninstallAll

```
Uninstall-AdcsEnrollmentWebService [-AllEnrollmentServices] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Uninstall-AdcsEnrollmentWebService` cmdlet uninstalls the Certificate Enrollment Web Service
either entirely removing all instances of it or partially by removing individual instances.

## EXAMPLES

### Example 1: Uninstall all Enrollment Web Service role services

```powershell
Uninstall-AdcsEnrollmentWebService -AllEnrollmentServices -Force
```

This command uninstalls all the Enrollment Web Service role services without prompting for
confirmation.

### Example 2: Uninstall an Enrollment Web Service role service using the specified CA

```powershell
$params = @{
    CAConfig           = "APP1.corp.contoso.com\corp-APP1-CA"
    AuthenticationType = Certificate
}
Uninstall-AdcsEnrollmentWebService @params
```

This command uninstalls the Certificate Enrollment Web Service using the CA specified by the
configuration named `APP1.corp.contoso.com\corp-APP1-CA`. The CA configuration is the CA Computer
Name and CA common name separated by a backslash. The authentication type in use is Certificate.

## PARAMETERS

### -AllEnrollmentServices

Indicates that this cmdlet removes all Certificate Enrollment Web Service instances.

```yaml
Type: SwitchParameter
Parameter Sets: UninstallAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthenticationType

Specifies the authentication type of the of enrollment services instance to be uninstalled.

```yaml
Type: AuthenticationType
Parameter Sets: UninstallSingleInstance
Aliases:
Accepted values: Kerberos, UserName, Certificate

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CAConfig

Specifies the configuration string of the certification authority (CA) for which this cmdlet
uninstalls enrollment services. This parameter is used to identify which instance of the Certificate
Enrollment Web Service is to be uninstalled when multiple are present.

```yaml
Type: String
Parameter Sets: UninstallSingleInstance
Aliases:

Required: True
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

### -Force

Forces the command to run without asking for user confirmation.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.CertificateServices.Deployment.Common.AuthenticationType

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Common.CES.EnrollmentServiceResult

## NOTES

- The application directories are removed from their respective instance folders in the file system.
  The uninstall command does not remove the Secure Sockets Layer/Transport Layer Security (SSL/TLS)
  or the secure hypertext transfer protocol (https) bindings.

## RELATED LINKS

[Install-AdcsEnrollmentWebService](./Install-AdcsEnrollmentWebService.md)
