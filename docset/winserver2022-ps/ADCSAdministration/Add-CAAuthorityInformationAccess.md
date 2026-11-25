---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsadministration/add-caauthorityinformationaccess?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-CAAuthorityInformationAccess
---

# Add-CAAuthorityInformationAccess

## SYNOPSIS
Configures the AIA or OCSP for a certification authority.

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
The **Add-CAAuthorityInformationAccess** cmdlet configures the uniform resource identifier (URI) for the Authority Information Access (AIA) or Online Certificate Status Protocol (OCSP) for a certification authority (CA).
An AIA URI should specify either an AIA extension or an OCSP extension, but not both.

## EXAMPLES

### Example 1: Add AIA to the specified authority

```powershell
Add-CAAuthorityInformationAccess -AddToCertificateAia -Uri http://ca1.corp.contoso.com/pki
```

This command adds Authority Information Access (AIA) for the specified certification authority to 'http://ca1.corp.contoso.com/pki'.

### Example 2: Add AIA for OCSP

```powershell
Add-CAAuthorityInformationAccess -AddToCertificateOcsp -Uri http://www.corp.contoso.com/ocsp.
```

This command adds AIA for OCSP pointing to `http://www.corp.contoso.com/ocsp`.

## PARAMETERS

### -AddToCertificateAia
Indicates the cmdlet adds the URI to the AIA extension of the issued certificate.

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
Indicates that the cmdlet adds the URI to the Online Responder OCSP extension of the issued certificate.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

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
Specifies a link, as a URI, for the AIA or Online Responder OCSP location.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.AuthorityInformationAccess

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.AuthorityInformationAccessResult
The cmdlet returns a Boolean type property named Restart, which, by default, is set to $True.

## NOTES

## RELATED LINKS

[Get-CAAuthorityInformationAccess](./Get-CAAuthorityInformationAccess.md)

[Remove-CAAuthorityInformationAccess](./Remove-CAAuthorityInformationAccess.md)

