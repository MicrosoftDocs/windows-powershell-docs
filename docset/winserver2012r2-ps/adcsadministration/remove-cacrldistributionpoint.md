---
author: Kateyanne
description: 
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
manager: jasgro
Module Name: adcsadministration
ms.author: v-kaunu
ms.date: 10/30/2017
ms.prod: powershell
ms.reviewer: brianlic
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/adcsadministration/remove-cacrldistributionpoint?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CACrlDistributionPoint
---

# Remove-CACrlDistributionPoint

## SYNOPSIS
Removes the URI for the certificate revocation list (CRL) distribution point (CDP) from the certification authority (CA).

## SYNTAX

```
Remove-CACrlDistributionPoint [-Uri] <String> [-AddToCertificateCdp] [-AddToFreshestCrl] [-AddToCrlCdp]
 [-AddToCrlIdp] [-PublishToServer] [-PublishDeltaToServer] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Remove-CACRLDistributionPoint cmdlet removes the uniform resource identifier (URI) for the certificate revocation list (CRL) distribution point from the certification authority (CA).

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-CACrlDistributionPoint -URI "http://corp.contoso.com/rootca.crl"
```

Description

-----------

Removes all URIs for all distribution points that contain the specified URI value ("http://corp.contoso.com/rootca.crl").

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Remove-CACrlDistributionPoint -Uri "http://corp.contoso.com/rootca.crl" -AddToCertificateCdp
```

Description

-----------

Removes only the URIs that are set to a value of "http://corp.contoso.com/rootca.crl" and for which the AddToCertificateCdp is set.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Remove-CACrlDistributionPoint -Uri "http://www.contoso.com/pki/orca.crl" -AddToCertificateCdp -AddToCrlIdp
```

Description

-----------

Removes only the uniform resource indicators (URIs) that are unique to the URI specified ("http://www.contoso.com/pki/orca.crl") and the combination of flags that are set or included (AddToCertificateCdp, AddToCrlIdp).

## PARAMETERS

### -AddToCertificateCdp
Remove from the CDP extension of issued certificates.

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
Remove from the certificate revocation list (CRL).

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
Remove from the IDP extension of issued certificates.

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
Remove from the most recent (freshest) certificate revocation list (CRL).

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
Remove the delta certificate revocation list (CRL).

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
Remove from the base certificate revocation list (CRL).

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.CrlDistributionPointResult
There is an output property named RestartCA, which when set to True indicates that the CA service (certsvc) needs to be restarted.

## NOTES

## RELATED LINKS

[Add-CACrlDistributionPoint](./Add-CACrlDistributionPoint.md)

[Get-CACrlDistributionPoint](./Get-CACrlDistributionPoint.md)

