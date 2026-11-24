---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsrelyingpartywebtheme?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsRelyingPartyWebTheme
---

# Get-AdfsRelyingPartyWebTheme

## SYNOPSIS
Gets properties of web themes applied to relying party trusts.

## SYNTAX

```
Get-AdfsRelyingPartyWebTheme [-RelyingPartyName <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsRelyingPartyWebTheme** cmdlet gets properties of any web themes applied to relying party trusts and the names of the trusts to which these themes are applied.

## EXAMPLES

### Example 1: Get a web theme
```
PS C:\> Get-AdfsRelyingPartyWebTheme -TargetRelyingPartyName "urn:app1"
```

This command gets the relying party web theme for the relying party named urn:app1.

## PARAMETERS

### -RelyingPartyName
Specifies an array of names of relying parties for which to get web themes.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AdfsRelyingPartyWebTheme](./Remove-AdfsRelyingPartyWebTheme.md)

[Set-AdfsRelyingPartyWebTheme](./Set-AdfsRelyingPartyWebTheme.md)

