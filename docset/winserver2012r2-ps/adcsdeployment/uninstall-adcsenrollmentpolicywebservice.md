---
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: adcsdeployment
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adcsdeployment/uninstall-adcsenrollmentpolicywebservice?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-AdcsEnrollmentPolicyWebService
---

# Uninstall-AdcsEnrollmentPolicyWebService

## SYNOPSIS
Uninstalls the Certificate Enrollment Policy Web service.

## SYNTAX

### UninstallSingleInstance (Default)
```
Uninstall-AdcsEnrollmentPolicyWebService -AuthenticationType <AuthenticationType> [-KeyBasedRenewal] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UninstallAll
```
Uninstall-AdcsEnrollmentPolicyWebService [-AllPolicyServers] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Uninstall-AdcsEnrollmentPolicyWebService cmdlet uninstalls the Certificate Enrollment Policy Web Service.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Uninstall-AdcsEnrollmentPolicyWebService -AllPolicyServers -force
```

Description

-----------

This command removes all configurations in the Certificate Enrollment Policy Web Service without prompting for confirmation.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Uninstall-AdcsEnrollmentPolicyWebService -AuthenticationType Certificate -KeyBasedRenewal -force
```

Description

-----------

This command removes the instance of Certificate Enrollment Policy Web Service that is utilizing certificate authentication and is in key-based renewal mode without prompting for confirmation.

## PARAMETERS

### -AllPolicyServers
Uninstall all instances of the Certificate Enrollment Policy (CEP) Web Service.

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
Specifies the authentication type for the Certificate Enrollment Policy (CEP) Web Service instance to be uninstalled when multiple instances are present.

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
Specifies the instance of the Certificate Enrollment Policy Web Service running in key-based renewal mode to be uninstalled.
This parameter is optional.
It is used to distinguish which instance of the Certificate Enrollment Policy Web Service is to be uninstalled if there are multiple instances that use the same authentication type.
If this option is not specified, the instance of the Certificate Enrollment Policy Web Service that is using the defined AuthenticationType that is not enabled for KeyBasedRenewal mode is uninstalled.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### bool, enum, bool

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.CEP.EnrollmentPolicyServiceResult

## NOTES
* Ensure you run Windows PowerShell as an administrator. You can use the -force switch to bypass the prompt for confirmation.

## RELATED LINKS

[Install-AdcsEnrollmentPolicyWebService](./Install-AdcsEnrollmentPolicyWebService.md)

