---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
ms.custom: has-azure-ad-ps-ref
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsazuremfatenant?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsAzureMfaTenant
---

# Set-AdfsAzureMfaTenant

## SYNOPSIS
Enables an AD FS farm to use MFA.

## SYNTAX

```
Set-AdfsAzureMfaTenant -TenantId <String> -ClientId <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsAzureMfaTenant** cmdlet enables an Active Directory Federation Services (AD FS) farm to use Azure Multi-Factor Authentication (MFA) after a certificate has been created and registered in the Microsoft Entra tenant.

## EXAMPLES

### Example 1: Enable Azure MFA
```
PS C:\> $certbase64 = New-AdfsAzureMfaTenantCertificate -TenantID <your tenant ID>
PS C:\> New-MsolServicePrincipalCredential -AppPrincipalId 981f26a1-7f43-403b-a875-f8b09b8cd720 -Type asymmetric -Usage verify -Value $certBase64
PS C:\> Set-AdfsAzureMfaTenant -TenantId <your tenant ID> -ClientId 981f26a1-7f43-403b-a875-f8b09b8cd720
```

This command creates a certificate for Azure MFA, registers it in the tenant, and enables Azure MFA on the AD FS farm.

### Example 2: Determine which certificate Azure MFA is using
```
$CertInBase64 = New-AdfsAzureMfaTenantCertificate -TenantID <your tenant ID> 
[Security.Cryptography.X509Certificates.X509Certificate2]([System.Convert]::FromBase64String($CertInBase64))
```

After AD FS has been configured for Azure MFA, this command determines which certificate Azure MFA is using and when it expires.

## PARAMETERS

### -ClientId
Specifies the well-known ID of the Azure MFA application in Microsoft Entra ID.

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

### -TenantId
Specifies the GUID representation of a Microsoft Entra tenant ID.
This can be found in the URL bar of the Microsoft Entra admin center, as in this example: 

`https://manage.windowsazure.com/contoso.onmicrosoft.com#Workspaces/ActiveDirectoryExtension/Directory/\<tenantID_GUID\>/directoryQuickStart`

You can also use the **Login-AzureRmAccount** cmdlet that is part of the Azure PowerShell module to get the tenant ID.

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

[New-AdfsAzureMfaTenantCertificate](./New-AdfsAzureMfaTenantCertificate.md)
