---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.KpsServer.Administration.dll-Help.xml
Module Name: HgsKeyProtection
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgskeyprotection/set-hgskeyprotectionattestationsignercertificatepolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-HgsKeyProtectionAttestationSignerCertificatePolicy
---

# Set-HgsKeyProtectionAttestationSignerCertificatePolicy

## SYNOPSIS
Modifies the policy for an attestation signer certificates.

## SYNTAX

```
Set-HgsKeyProtectionAttestationSignerCertificatePolicy -DenyHealthCertificatesIssuedBefore <DateTime>
 [-Thumbprint <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-HgsKeyProtectionAttestationSignerCertificatePolicy** cmdlet modifies the policy for attestation signer certificates.
You can modify a date in the policy.
The Key Protection Service rejects health certificates signed by the specified attestation signer certificate and issued before the specified date.

## EXAMPLES

### Example 1: Modify the date on all attestation signer certificates
```
PS C:\> $DenyTime = Get-Date
PS C:\> Set-HgsKeyProtectionAttestationSignerCertificatePolicy -DenyHealthCertificatesIssuedBefore $DenyTime
```

The first command creates a **DateTime** object by using the **Get-Date** cmdlet, and then stores it in the **$DenyTime** variable.

The second command modifies the date for all trusted attestation signer certificates to the value stored in **$DenyTime**.

### Example 2: Modify the date on an attestation signer certificate
```
PS C:\> $DenyTime = Get-Date
PS C:\> Set-HgsKeyProtectionAttestationSignerCertificatePolicy -DenyHealthCertificatesIssuedBefore $DenyTime -Thumbprint "8bdc4fb5034c4adb86cb57a4465dc161"
```

The first command creates a **DateTime** object, and then stores it in the **$DenyTime** variable.

The second command modifies the date for a specific trusted attestation signer certificate to the value stored in **$DenyTime**.

## PARAMETERS

### -DenyHealthCertificatesIssuedBefore
Specifies a date as a **DateTime** object.
The Key Protection Service rejects any health certificates signed by the specified attestation signer certificate and issued before this time.
To obtain a **DateTime** object, use the [Get-Date](https://go.microsoft.com/fwlink/?LinkID=293966) cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: True
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

### -Thumbprint
Specifies the thumbprint of the attestation signer certificate to which to apply the policy.
If you do not specify a value for this parameter, this cmdlet applies the policy to all signer certificates.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-HgsKeyProtectionAttestationSignerCertificate](./Get-HgsKeyProtectionAttestationSignerCertificate.md)

