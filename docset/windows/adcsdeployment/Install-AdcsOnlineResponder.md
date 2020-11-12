---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Deployment.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/27/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Install-AdcsOnlineResponder
ms.reviewer:
ms.assetid: 461DA0B7-62C8-4299-9A58-42C4F15146F5
---

# Install-AdcsOnlineResponder

## SYNOPSIS
Installs the Online Responder service.

## SYNTAX

```
Install-AdcsOnlineResponder [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-AdcsOnlineResponder** cmdlet installs the Online Responder service, which provides Online Certificate Status Protocol (OSCP) services.
To remove the role service, use the **Uninstall-AdcsOnlineResponder** cmdlet.

You can import the cmdlet by running the following commands from Windows PowerShell:

- `Import-Module ServerManager`
- `Add-WindowsFeature Adcs-Online-Cert`

## EXAMPLES

### Example 1: Install the Online Responder role service
```
PS C:\> Install-AdcsOnlineResponder
```

This command installs the Online Responder role service.

### Example 2: Force the installation of the Online Responder role service
```
PS C:\> Install-AdcsOnlineResponder -Force
```

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
Specifies a **PSCredential** object for the Online Responder service.
To obtain a credential object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSCredential

## OUTPUTS

### Microsoft.CertificateServices.Deployment.Commands.OCSP.OnlineResponderResult

## NOTES
* Ensure you run Windows PowerShell as an administrator. You can use the *Force* parameter to bypass the prompt for confirmation.
To see parameters, run the following command: `Install-AdcsOnlineResponder -?`

## RELATED LINKS

[Uninstall-AdcsOnlineResponder](./Uninstall-AdcsOnlineResponder.md)

[Get-Credential](https://go.microsoft.com/fwlink/?LinkID=293936)

