---
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
Module Name: adcsdeployment
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adcsdeployment/install-adcsonlineresponder?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-AdcsOnlineResponder
---

# Install-AdcsOnlineResponder

## SYNOPSIS
Installs Online Responder service

## SYNTAX

```
Install-AdcsOnlineResponder [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Install-AdcsOnlineResponder configures the Online Responder service, which provides Online Certificate Status Protocol (OSCP) services.
To remove the role service, use the Uninstall-AdcsOnlineResponder cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:
Import-Module ServerManager
Add-WindowsFeature Adcs-Online-Cert

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Install-AdcsOnlineResponder
```

Description

-----------

This command installs the Online Responder role service.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Install-AdcsOnlineResponder -force
```

Description

-----------

This command forces the installation of the Online Responder role service.

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

### -Credential
You can install the Online Responder role service only on servers that are members of Active Directory Domain Services (AD DS) domains.
If you are installing an online responder configured to use a standalone certification authority (CA), then an account that is a member of the local Administrators group of the target server is required.
If you are installing an online responder to target an Enterprise CA, then an account that is a member of the Domain Admins group is required.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSCredential

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.OCSP.OnlineResponderResult

## NOTES
* Ensure you run Windows PowerShell® as an administrator. You can use the -force switch to bypass the prompt for confirmation.
To see parameters, run the following command: install-AdcsOnlineResponder -?

## RELATED LINKS

[Uninstall-AdcsOnlineResponder](./Uninstall-AdcsOnlineResponder.md)

