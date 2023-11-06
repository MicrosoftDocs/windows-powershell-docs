---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
ms.custom: has-azure-ad-ps-ref
online version: https://learn.microsoft.com/powershell/module/adfs/new-adfsazuremfatenantcertificate?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AdfsAzureMfaTenantCertificate
---

# New-AdfsAzureMfaTenantCertificate

## SYNOPSIS
Creates a certificate for the AD FS farm to use to connect to Azure MFA, or returns the currently configured certificate.

## SYNTAX

```
New-AdfsAzureMfaTenantCertificate -TenantId <String> [-Renew <Boolean>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AdfsAzureMfaTenantCertificate** cmdlet creates a certificate for an Active Directory Federation Services (AD FS) farm to use to connect to Azure Multi-Factor Authentication (MFA), or returns the currently configured certificate.

The cmdlet looks in the local machine My store for a certificate with Issuer and Subject equal to: 

- `CN = <tenant ID>`
- `OU = Microsoft AD FS Azure MFA`

If it does not find one, it generates it.

## EXAMPLES

### Example 1: Create a certificate and enable Azure MFA on an AD FS farm
```
PS C:\> $certbase64 = New-AdfsAzureMfaTenantCertificate -TenantID <your tenant ID>
PS C:\> New-AzureADServicePrincipalKeyCredential -ObjectId 981f26a1-7f43-403b-a875-f8b09b8cd720 -Type asymmetric -Usage verify -Value $certBase64
PS C:\> Set-AdfsAzureMfaTenant -TenantId <your tenant ID> -ClientId 981f26a1-7f43-403b-a875-f8b09b8cd720
```

These commands create a certificate for Azure MFA, register the certificate in a tenant, and enable Azure MFA on an AD FS farm.

> [!NOTE]
> Customers are encouraged to use the newer Azure Active Directory PowerShell 2.0 module. For more information about the v2.0 module, see [AzureAD PowerShell 2.0](/powershell/module/Azuread/?view=azureadps-2.0).

### Example 2: Determine which certificate Azure MFA is using
```
$CertInBase64 = New-AdfsAzureMfaTenantCertificate -TenantID
$cert = Security.Cryptography.X509Certificates.X509Certificate2
$cert | Format-List *
```

After AD FS has been configured for Azure MFA, this command determines which certificate Azure MFA is using and when it expires.

## PARAMETERS

### -Renew
Renew certificate. Do not use if the certificate has already expired. In this scenario, the existing expired certificate is replaced with a new certificate.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TenantId
Specifies the GUID representation of the Microsoft Entra tenant ID.
This can be found in the URL bar of the Microsoft Entra admin center, as in this example: `https://manage.windowsazure.com/contoso.onmicrosoft.com#Workspaces/ActiveDirectoryExtension/Directory/<tenantID_GUID>/directoryQuickStart`

Alternatively, you can use the **Login-AzureRmAccount** cmdlet to get the tenant ID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Default value: False
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AdfsAzureMfaTenant](./Set-AdfsAzureMfaTenant.md)
