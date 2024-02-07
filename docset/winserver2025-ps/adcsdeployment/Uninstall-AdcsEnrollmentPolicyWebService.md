---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: ADCSDeployment
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsdeployment/uninstall-adcsenrollmentpolicywebservice?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-AdcsEnrollmentPolicyWebService
---

# Uninstall-AdcsEnrollmentPolicyWebService

## SYNOPSIS
Uninstalls the Certificate Enrollment Policy Web service.

## SYNTAX

### UninstallSingleInstance (Default)

```
Uninstall-AdcsEnrollmentPolicyWebService -AuthenticationType <AuthenticationType>
 [-KeyBasedRenewal] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UninstallAll

```
Uninstall-AdcsEnrollmentPolicyWebService [-AllPolicyServers] [-Force] 
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Uninstall-AdcsEnrollmentPolicyWebService` cmdlet uninstalls the Certificate Enrollment Policy
(CEP) Web Service.

## EXAMPLES

### Example 1: Uninstall all configuration in the CEP Web Service

```powershell
Uninstall-AdcsEnrollmentPolicyWebService -AllPolicyServers -Force
```

This command uninstalls all configurations in the CEP Web Service without prompting for
confirmation.

### Example 2: Uninstall an instance of the CEP Web Service

```powershell
Uninstall-AdcsEnrollmentPolicyWebService -AuthenticationType Certificate -KeyBasedRenewal -Force
```

This command uninstalls the instance of CEP Web Service that is utilizing certificate authentication
and is in key-based renewal mode without prompting for confirmation.

## PARAMETERS

### -AllPolicyServers

Indicates that the cmdlet uninstall all instances of the CEP Web Service.

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

Specifies the authentication type for the CEP Web Service instance to be uninstalled when multiple
instances are present.

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

### -KeyBasedRenewal

Indicates that this cmdlet uninstalls the instance of the CEP Web Service running in key-based
renewal mode. This parameter is optional. It is used to distinguish which instance of the CEP Web
Service is to be uninstalled if there are multiple instances that use the same authentication type.
If this option is not specified, the instance of the CEP Web Service that is using the defined
AuthenticationType that is not enabled for KeyBasedRenewal mode is uninstalled.

```yaml
Type: SwitchParameter
Parameter Sets: UninstallSingleInstance
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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Management.Automation.SwitchParameter

### Microsoft.CertificateServices.Deployment.Common.AuthenticationType

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Common.CEP.EnrollmentPolicyServiceResult

## NOTES

- Ensure you run Windows PowerShell as an administrator. You can use the **Force** parameter to
  bypass the prompt for confirmation.

## RELATED LINKS

[Install-AdcsEnrollmentPolicyWebService](./Install-AdcsEnrollmentPolicyWebService.md)

