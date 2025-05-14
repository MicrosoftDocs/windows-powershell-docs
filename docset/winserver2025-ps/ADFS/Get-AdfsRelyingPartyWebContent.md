---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsrelyingpartywebcontent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsRelyingPartyWebContent
---

# Get-AdfsRelyingPartyWebContent

## SYNOPSIS
Gets web content objects for relying parties.

## SYNTAX

```
Get-AdfsRelyingPartyWebContent [-Locale <CultureInfo>] [-RelyingPartyName <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsRelyingPartyWebContent** cmdlet gets web content objects for relying parties.
Specify a relying party by name.
If you do not specify a name, the cmdlet gets all relying party web content objects.
If you do not specify a locale, the cmdlet gets web content for all locales.

## EXAMPLES

### Example 1: Get all web content objects
```
PS C:\> Get-AdfsRelyingPartyWebContent
```

This command gets web content objects for all relying parties and locales.

### Example 2: Get web content objects for a specified relying party
```
PS C:\> Get-AdfsRelyingPartyWebContent -Name "RelyingParty01"
```

This command gets web content objects for the relying party named RelyingParty01 for all locales.

### Example 3: Get the web content object for a specified relying party and locale
```
PS C:\> Get-AdfsRelyingPartyWebContent -Locale en-us -Name "RelyingParty01"
```

This command gets web content objects for the relying party named RelyingParty01 for the specified locale.

## PARAMETERS

### -Locale
Specifies a locale.
The cmdlet gets relying party web content for the locale that you specify.

```yaml
Type: CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RelyingPartyName
Specifies an array of names of relying parties.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent, Microsoft.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent[]
This cmdlet generates a **System.IdentityServer.Management.Resources.AdfsRelyingPartyWebContent** object that represents web content of a relying party, or an array of such objects.
The object includes the following properties:

- Locale: **System.Globalization.CultureInfo**
- Name: **System.String**
- ErrorPageGenericErrorMessage: **System.String**
- ErrorPageAuthorizationErrorMessage: **System.String**
- ErrorPageDeviceAuthenticationErrorMessage: **System.String**

## NOTES

## RELATED LINKS

[Remove-AdfsRelyingPartyWebContent](./Remove-AdfsRelyingPartyWebContent.md)

[Set-AdfsRelyingPartyWebContent](./Set-AdfsRelyingPartyWebContent.md)

