---
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
online version: 
schema: 2.0.0
title: Remove-CAAuthorityInformationAccess
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 8A3ABA4F-7422-48DD-AA60-A943E8D31474
---

# Remove-CAAuthorityInformationAccess

## SYNOPSIS
Removes authority information access (AIA) or Online Certificate Status Protocol (OCSP) URI from the AIA extension set on the certification authority.

## SYNTAX

### RemoveAsAIA (Default)
```
Remove-CAAuthorityInformationAccess [-Uri] <String> [-AddToCertificateAia] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RemoveAsOCSP
```
Remove-CAAuthorityInformationAccess [-Uri] <String> [-AddToCertificateOcsp] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Remove-CAAuthorityInformationAccess cmdlet removes the Authority Information Access (AIA) or Online Certificate Status Protocol (OCSP) URI from the AIA extension set on the certification authority.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-CAAuthorityInformationAccess -uri "http://www.contoso.com/pki/orca1.crt" -AddToCertificateAia
```

Description

-----------

Removes Authority Information Access (AIA) for the specified uniform resource identifier (URI) of 'http://www.contoso.com/pki/orca1.crt'.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Remove-CAAuthorityInformationAccess -uri "http://www.cpandl.com/ocsp/" -AddToCertificateOcsp
```

Description

-----------

Removes the Online Certificate Status Protocol (OCSP) for the specified uniform resource identifier (URI) of 'http://www.cpandl.com/ocsp'.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Remove-CAAuthorityInformationAccess -uri "http://www.contoso.com/pki/orca1.crt"
```

Description

-----------

Removes all AIA and OCSP entries that match the URL 'http://www.contoso.com/pki/orca1.crt'.

## PARAMETERS

### -AddToCertificateAia
This switch indicates the Authority Information Access (AIA) uniform resource information (URI).

```yaml
Type: SwitchParameter
Parameter Sets: RemoveAsAIA
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddToCertificateOcsp
This switch indicates an Online Responder's uniform resource information (URI).

```yaml
Type: SwitchParameter
Parameter Sets: RemoveAsOCSP
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

### -Uri
Specifies the uniform resource identifier (URI) from where the certificate for the certification authority (CA) can be downloaded or the online responder information can be obtained.
This information is added to the CA properties and registry.

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

### Microsoft.CertificateServices.Administration.Commands.CA.AuthorityInformationAccessResult

## NOTES
* You must be a member of Enterprise Admins group to successfully run this command.

## RELATED LINKS

[Add-CAAuthorityInformationAccess](./Add-CAAuthorityInformationAccess.md)

[Get-CAAuthorityInformationAccess](./Get-CAAuthorityInformationAccess.md)

