---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsadministration/add-cacrldistributionpoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-CACrlDistributionPoint
---

# Add-CACrlDistributionPoint

## SYNOPSIS
Adds a CRL distribution point URI where AD CS publishes certification revocations.

## SYNTAX

```
Add-CACrlDistributionPoint [-Uri] <String> [-AddToCertificateCdp] [-AddToFreshestCrl] [-AddToCrlCdp]
 [-AddToCrlIdp] [-PublishToServer] [-PublishDeltaToServer] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-CACRLDistributionPoint** cmdlet adds a certificate revocation list (CRL) distribution point uniform resource indicator (URI) where Active Directory Certificate Services (AD CS) publishes certification revocations.

You can add CRL distribution points in issued certificates by using this Windows PowerShell cmdlet.
However, adding the URL for a CRL distribution point only affects newly issued certificates.
Previously issued certificates will continue to reference the original location.

To indicate that you want to use a URL as a CRL distribution point, use the switch parameter *PublishCRL*.

To indicate that you want to use a URL as a delta CRL distribution point, use the switch parameter *PublishDeltaCRL*.

To indicate that you want to publish this location in CRLs to point clients to a delta CRL, use the switch parameter *IncludeDeltaCRLs*.

CRL uniform resource locators can be HTTP or Lightweight Directory Access Protocol (LDAP) paths.
You can use the following variables depending upon the switch when specifying the address of the CRL.

`<CAName>`, which is replaced by the name of the targeted CA.

`<CAObjectClass>`, which is replaced by object class identifier for a CA, used when publishing to an LDAP URL.

`<CATruncatedName>`, which is replaced by sanitized name of the CA, truncated to 32 characters with a hash at the end.

`<CDPObjectClass>`, which is replaced by the object class identifier for CRL distribution points, used when publishing to an LDAP URL.

`<CertificateName>`, which is replaced by the renewal extension of the CA.

`<ConfigurationContainer>`, which is replaced by the location of the Configuration container in Active Directory Domain Services (AD DS) location.

`<CRLNameSuffix>`, which is replaced by inserts a name suffix at the end of the file name when publishing a CRL to a file or URL.

`<DeltaCRLAllowed>`, which is replaced by the CRLNameSuffix variable with a separate suffix to distinguish the delta CRL from the CRL; used when a delta CRL is published.

`<ServerDNSName>`, which is replaced by the DNS name of the CA server.

`<ServerShortName>`, which is replaced by the NetBIOS name of the CA server.

## EXAMPLES

### Example 1: Add a CRL distribution point URI where AD CS publishes certification revocations
```
PS C:\> Add-CACRLDistributionPoint -Uri "http://ca1.corp.contoso.com/pki/<CAName>.crl" -AddToCertificateCdp
```

This command adds a CRL distribution point for the URI of `http://ca1.corp.contoso.com/pki/<CAName>.crl` and sets the CRL URI to be included in issued certificates.

## PARAMETERS

### -AddToCertificateCdp
Indicates that the cmdlet adds the CDP extension of issued certificates.
This parameter is available for use with LDAP, HTTP, Universal Naming Convention (UNC), and File paths.

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
Indicates that the cmdlet includes the CRL.
This parameter is available for use with LDAP paths.

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
Indicates that the cmdlet includes the IDP extension of issued certificates.
This parameter is available for use with LDAP and HTTP paths.

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
Indicates that the cmdlet includes the most recent CRL.
This parameter is available for use with LDAP, HTTP, UNC, and file paths.

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
Indicates that the cmdlet publishes the delta CRL.
This parameter is available for use with LDAP, UNC, local, and file paths.

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
Indicates that the cmdlet publishes the CRL to the specified server.
This parameter is available for use with LDAP, local, UNC, and file paths.

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
Specifies the uniform resource identifier (URI) for the distribution point location of the CRL.
This is the location from where status information about certificate revocation will be retrieved and the location the CRL will be published.

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
This cmdlet returns a Boolean object named Restart.
If Restart equals True, then the CA must be restarted.

## NOTES

## RELATED LINKS

[Get-CACrlDistributionPoint](./Get-CACrlDistributionPoint.md)

[Remove-CACrlDistributionPoint](./Remove-CACrlDistributionPoint.md)

