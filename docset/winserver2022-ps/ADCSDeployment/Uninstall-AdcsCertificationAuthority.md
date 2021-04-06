---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
manager: jasgro
Module Name: ADCSDeployment
ms.author: v-kaunu
ms.date: 12/27/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/adcsdeployment/uninstall-adcscertificationauthority?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-AdcsCertificationAuthority
---

# Uninstall-AdcsCertificationAuthority

## SYNOPSIS
Uninstalls the CA role service and removes the configuration information.

## SYNTAX

```
Uninstall-AdcsCertificationAuthority [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-AdcsCertificationAuthority** cmdlet removes the Active certificate authority (CA) role and removes the configuration information.

## EXAMPLES

### Example 1: Uninstall the Active Directory CA role service
```
PS C:\> Uninstall-AdcsCertificationAuthority -Force
```

This command uninstalls the Active Directory Certification Authority role service and does not prompt for user confirmation.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.CA.CertificationAuthoritySetupResult

## NOTES
* To uninstall the CA role service, ensure you run Windows PowerShell as an administrator. You can run the command with the *Force* parameter to bypass the prompt for confirmation.

## RELATED LINKS

[Install-AdcsCertificationAuthority](./Install-AdcsCertificationAuthority.md)

