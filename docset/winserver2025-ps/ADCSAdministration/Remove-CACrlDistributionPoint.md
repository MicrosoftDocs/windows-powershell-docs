---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsadministration/remove-cacrldistributionpoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CACrlDistributionPoint
---

# Remove-CACrlDistributionPoint

## SYNOPSIS
Removes the URI for the CRL distribution point (CDP) from the CA.

## SYNTAX

```
Remove-CACrlDistributionPoint [-Uri] <String> [-AddToCertificateCdp] [-AddToFreshestCrl] [-AddToCrlCdp]
 [-AddToCrlIdp] [-PublishToServer] [-PublishDeltaToServer] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-CACRLDistributionPoint** cmdlet removes the uniform resource identifier (URI) for the certificate revocation list (CRL) distribution point from the certification authority (CA).

## EXAMPLES

### Example 1: Remove all URIs for all distribution points for the specified URI
```
PS C:\> Remove-CACrlDistributionPoint -URI "http://corp.contoso.com/rootca.crl"
```

This command removes all URIs for all distribution points that contain the specified URI value `http://corp.contoso.com/rootca.crl`.

### Example 2: Remove the URIs for all distribution points for the CDP extension of issued certificates
```
PS C:\> Remove-CACrlDistributionPoint -Uri "http://corp.contoso.com/rootca.crl" -AddToCertificateCdp
```

This command removes only the URIs that are set to a value of `http://corp.contoso.com/rootca.crl` and for which the *AddToCertificateCdp* parameter is set.

### Example 3: Remove the URIs for all distribution points for the CDP and IDP extensions of issued certificates
```
PS C:\> Remove-CACrlDistributionPoint -Uri "http://www.contoso.com/pki/orca.crl" -AddToCertificateCdp -AddToCrlIdp
```

This command removes only the URIs that are unique to the URI named `http://www.contoso.com/pki/orca.crl` and the combination of flags that are set or included with the *AddToCertificateCdp* and *AddToCrlIdp* parameters.

## PARAMETERS

### -AddToCertificateCdp
Indicates that the cmdlet removes the CDP extension of issued certificates.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddToCrlCdp
Indicates that the cmdlet removes the CRL.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddToCrlIdp
Indicates that the cmdlet removes the IDP extension of issued certificates.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddToFreshestCrl
Indicates that the cmdlet removes the most recent CRL.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
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

### -PublishDeltaToServer
Indicates that the cmdlet removes the delta CRL.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishToServer
Indicates that the cmdlet removes the base CRL.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Uri
Specifies the uniform resource identifier (URI) for the distribution point location of the certificate revocation list (CRL).
This is the location from where status information about certificate revocation has been retrieved and/or the location the CRL was published.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.CrlDistributionPointResult
This cmdlet returns a property named RestartCA, which when set to True indicates that the CA service (certsvc) needs to be restarted.

## NOTES

## RELATED LINKS

[Add-CACrlDistributionPoint](./Add-CACrlDistributionPoint.md)

[Get-CACrlDistributionPoint](./Get-CACrlDistributionPoint.md)

