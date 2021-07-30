---
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: adcsdeployment
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adcsdeployment/uninstall-adcscertificationauthority?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-AdcsCertificationAuthority
---

# Uninstall-AdcsCertificationAuthority

## SYNOPSIS
Uninstalls the Certification Authority (CA) role service and removes its configuration information.

## SYNTAX

```
Uninstall-AdcsCertificationAuthority [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Uninstall-AdcsCertificationAuthority cmdlet removes the Active CA role and removes its configuration information.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Uninstall-AdcsCertificationAuthority -force
```

Description

-----------

This command removes the Active Directory Certification Authority role service and does not prompt for user confirmation.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.CA.CertificationAuthoritySetupResult

## NOTES
* To uninstall the CA role service, ensure you run PowerShell as an administrator. You can run the command with the -f switch to bypass the prompt for confirmation.

## RELATED LINKS

[Install-AdcsCertificationAuthority](./Install-AdcsCertificationAuthority.md)

