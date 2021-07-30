---
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: adcsadministration
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adcsadministration/add-caauthorityinformationaccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-CAAuthorityInformationAccess
---

# Add-CAAuthorityInformationAccess

## SYNOPSIS
Configures the Authority Information Access (AIA) or Online Certificate Status Protocol (OCSP) for a certification authority (CA).

## SYNTAX

### AddAsInputObject
```
Add-CAAuthorityInformationAccess [-InputObject] <AuthorityInformationAccess> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AddAsOCSP
```
Add-CAAuthorityInformationAccess [-Uri] <String> [-AddToCertificateOcsp] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AddAsAIA
```
Add-CAAuthorityInformationAccess [-Uri] <String> [-AddToCertificateAia] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Add-CAAuthorityInformationAccess cmdlet configures the uniform resource identifier (URI) for the AIA or Online Responder OCSP location for a CA.
An AIA URI should specify either an AIA extension or an OCSP extension, but not both.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>Add-CAAuthorityInformationAccess -AddToCertificateAia -uri https://ca1.corp.contoso.com/pki
```

Description

-----------

Adds Authority Information Access (AIA) for the specified certification authority to https://ca1.corp.contoso.com/pki

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\>Add-CAAuthorityInformationAccess -AddToCertificateOcsp -uri https://www.corp.contoso.com/ocsp
```

Description

-----------

Adds AIA for OCSP pointing to https://www.corp.contoso.com/ocsp

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\>$aia = Get-CAAuthorityInformationAccess


PS C:\>$aia | remove-CAAuthorityInformationAccess
```

These commands remove all AIA entries

## PARAMETERS

### -AddToCertificateAia
Specifies to add the URI to the AIA extension of the issued certificate.

```yaml
Type: SwitchParameter
Parameter Sets: AddAsAIA
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddToCertificateOcsp
Specifies to add the URI to the Online Responder OCSP extension of the issued certificate.

```yaml
Type: SwitchParameter
Parameter Sets: AddAsOCSP
Aliases: 

Required: True
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Suppresses all user prompts.
By default, you are prompted to confirm each operation.

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

### -InputObject
The input object is meant to be used in a pipeline command.

```yaml
Type: AuthorityInformationAccess
Parameter Sets: AddAsInputObject
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Uri
Specifies a URI for the AIA or Online Responder OCSP location.

```yaml
Type: String
Parameter Sets: AddAsOCSP, AddAsAIA
Aliases: 

Required: True
Position: 1
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.AuthorityInformationAccessResult
This output object has a single property named Restart of Boolean type, which by default is set to True.

## NOTES

## RELATED LINKS

[Get-CAAuthorityInformationAccess](./Get-CAAuthorityInformationAccess.md)

[Remove-CAAuthorityInformationAccess](./Remove-CAAuthorityInformationAccess.md)

