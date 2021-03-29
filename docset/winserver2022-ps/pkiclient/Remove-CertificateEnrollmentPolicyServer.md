---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.PKIClient.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-CertificateEnrollmentPolicyServer
ms.reviewer:
ms.assetid: 048D5F06-8277-4CC7-A827-84C2FA4D3904
---

# Remove-CertificateEnrollmentPolicyServer

## SYNOPSIS
Removes an enrollment policy server and the URL of the enrollment policy server from the current user or local computer configuration.

## SYNTAX

```
Remove-CertificateEnrollmentPolicyServer [-Url] <Uri> -context <Context> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-CertificateEnrollmentPolicyServer** cmdlet removes an enrollment policy server from the current user or local computer configuration.
This cmdlet also removes any policy cache file and credentials from the vault.

Only one enrollment policy server configuration is removed from the user configured location at a time. 

If a scope of All is specified and the same URL exists in the local computer (machine) and User contexts, then this cmdlet will fail. 

An error is generated if the specified URL does not exist in the given scope. 

Any policy cache file and credentials are also removed from the vault.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-CertificateEnrollmentPolicyServer -Url https://www.contoso.com/policy/service.svc -Context User
```

This example removes the enrollment policy server configuration from the local user configuration with the given URL.

### EXAMPLE 2
```
PS C:\>$userPolicy = Get-CertificateEnrollmentPolicyServer -Scope All -Context User -Url https://www.contoso.com/policy/service.svc

PS C:\>Remove-CertificateEnrollmentPolicyServer -Url $userPolicy.url -Context User
```

This example removes the enrollment policy server that is configured from the current user configuration.

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

### -Url
Specifies the URL of the enrollment policy server to remove from the local configuration.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -context
Specifies that information about the location of an enrollment policy server should be removed from either the User or computer (machine) context.

```yaml
Type: Context
Parameter Sets: (All)
Aliases: 
Accepted values: Machine, User

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Commands.EnrollmentPolicyServer
Contains information about the certificate enrollment policy.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-CertificateEnrollmentPolicyServer](./Add-CertificateEnrollmentPolicyServer.md)

[Get-CertificateEnrollmentPolicyServer](./Get-CertificateEnrollmentPolicyServer.md)

