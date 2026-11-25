---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.CertificateServices.Administration.Commands.dll-Help.xml
Module Name: ADCSAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/adcsadministration/remove-caauthorityinformationaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CAAuthorityInformationAccess
---

# Remove-CAAuthorityInformationAccess

## SYNOPSIS
Removes AIA or OCSP URI from the AIA extension set on the certification authority.

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
The **Remove-CAAuthorityInformationAccess** cmdlet removes the Authority Information Access (AIA) or Online Certificate Status Protocol (OCSP) uniform resource information (URI) from the AIA extension set on the certification authority.

## EXAMPLES

### Example 1: Remove AIA for a specified URI
```
PS C:\> Remove-CAAuthorityInformationAccess -Uri "http://www.contoso.com/pki/orca1.crt" -AddToCertificateAia
```

This command removes AIA for the specified URI named `http://www.contoso.com/pki/orca1.crt`.

### Example 2: Remove OCSP for a specified URI
```
PS C:\> Remove-CAAuthorityInformationAccess -Uri "http://www.cpandl.com/ocsp/" -AddToCertificateOcsp
```

This command removes the OCSP for the specified URI named `http://www.cpandl.com/ocsp`.

### Example 3: Remove all AIA and OCSP entries for a specified URI
```
PS C:\> Remove-CAAuthorityInformationAccess -Uri "http://www.contoso.com/pki/orca1.crt"
```

This command removes all AIA and OCSP entries that match the URL `http://www.contoso.com/pki/orca1.crt`.

### Example 4: Remove all AIA entries

```powershell
$AIA = Get-CAAuthorityInformationAccess
$AIA | Remove-CAAuthorityInformationAccess
```

This example removes all AIA entries

The first command gets the certificate authority information and stores the information in the variable named $AIA.

The second command removes all the AIA entries that are stored in the $AIA variable.
## PARAMETERS

### -AddToCertificateAia
Indicates that the cmdlet adds the AIA URI.

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
Indicates that the cmdlet adds an Online Responder's URI.

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
Specifies the URI from where the certificate for the CA can be downloaded or the online responder information can be obtained.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.CertificateServices.Administration.Commands.CA.AuthorityInformationAccessResult

## NOTES
* You must be a member of Enterprise Admins group to successfully run this command.

## RELATED LINKS

[Add-CAAuthorityInformationAccess](./Add-CAAuthorityInformationAccess.md)

[Get-CAAuthorityInformationAccess](./Get-CAAuthorityInformationAccess.md)

