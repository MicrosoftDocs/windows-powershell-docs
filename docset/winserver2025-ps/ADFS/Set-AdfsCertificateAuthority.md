---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfscertificateauthority?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsCertificateAuthority
---

# Set-AdfsCertificateAuthority

## SYNOPSIS
Modifies a certificate authority.

## SYNTAX

### SelfIssued
```
Set-AdfsCertificateAuthority [-SelfIssued] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RolloverSigningCertificate
```
Set-AdfsCertificateAuthority [-RolloverSigningCertificate] [-ForcePromotion] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### EnrollmentAgentConfiguration
```
Set-AdfsCertificateAuthority [-EnrollmentAgent] [-CertificateAuthority <String>]
 [-LogonCertificateTemplate <String>] [-WindowsHelloCertificateTemplate <String>]
 [-EnrollmentAgentCertificateTemplate <String>] [-AutoEnrollEnabled <Boolean>]
 [-CertificateGenerationThresholdDays <Int32>] [-WindowsHelloCertificateProxyEnabled <Boolean>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsCertificateAuthority** cmdlet modifies a certificate authority in Active Directory Federation Services (AD FS).

## EXAMPLES

## PARAMETERS

### -AutoEnrollEnabled
{{Fill AutoEnrollEnabled Description}}

```yaml
Type: Boolean
Parameter Sets: EnrollmentAgentConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateAuthority
Specifies a certificate authority.

```yaml
Type: String
Parameter Sets: EnrollmentAgentConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateGenerationThresholdDays
{{Fill CertificateGenerationThresholdDays Description}}

```yaml
Type: Int32
Parameter Sets: EnrollmentAgentConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnrollmentAgent
```yaml
Type: SwitchParameter
Parameter Sets: EnrollmentAgentConfiguration
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnrollmentAgentCertificateTemplate
```yaml
Type: String
Parameter Sets: EnrollmentAgentConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForcePromotion
```yaml
Type: SwitchParameter
Parameter Sets: RolloverSigningCertificate
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogonCertificateTemplate
```yaml
Type: String
Parameter Sets: EnrollmentAgentConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -RolloverSigningCertificate
```yaml
Type: SwitchParameter
Parameter Sets: RolloverSigningCertificate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelfIssued
Indicates whether the certificate authority is self-issued.

```yaml
Type: SwitchParameter
Parameter Sets: SelfIssued
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsHelloCertificateProxyEnabled
{{Fill WindowsHelloCertificateProxyEnabled Description}}

```yaml
Type: Boolean
Parameter Sets: EnrollmentAgentConfiguration
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsHelloCertificateTemplate
{{Fill WindowsHelloCertificateTemplate Description}}

```yaml
Type: String
Parameter Sets: EnrollmentAgentConfiguration
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.AdfsCertificateAuthority

Returns the updated AdfsCertificateAuthority object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Disable-AdfsCertificateAuthority](./Disable-AdfsCertificateAuthority.md)

[Get-AdfsCertificateAuthority](./Get-AdfsCertificateAuthority.md)

