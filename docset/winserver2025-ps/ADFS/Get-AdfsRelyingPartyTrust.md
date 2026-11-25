---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsrelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsRelyingPartyTrust
---

# Get-AdfsRelyingPartyTrust

## SYNOPSIS
Gets the relying party trusts of the Federation Service.

## SYNTAX

### RelyingPartyName (Default)
```
Get-AdfsRelyingPartyTrust [[-Name] <String[]>] [<CommonParameters>]
```

### Identifier
```
Get-AdfsRelyingPartyTrust [-Identifier] <String[]> [<CommonParameters>]
```

### PrefixIdentifier
```
Get-AdfsRelyingPartyTrust [-PrefixIdentifier] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsRelyingPartyTrust** cmdlet gets the relying party trusts of the Federation Service.
You can use this cmdlet with no parameters to get all relying party trust objects.

## EXAMPLES

### Example 1: Get property settings for a relying party trust by using a name
```
PS C:\> Get-AdfsRelyingPartyTrust -Name "FabrikamApp"
```

This command gets the property settings for the relying party trust named FabrikamApp.

### Example 2: Get property settings for a relying party trust by using an identifier
```
PS C:\> Get-AdfsRelyingPartyTrust -Identifier "https://FabrikamApp.CentralServer.org"
```

This command gets the property settings for a relying party trust that has the identifier `https://FabrikamApp.CentralServer.org`.

### Example 3: Get property settings for an updated relying party trust
```
PS C:\> Get-AdfsRelyingPartyTrust | Where-Object{ $_.LastUpdateTime -le (get-date).subtract((new-timespan -hours 24))}
```

This command gets the property settings for relying party trusts that have been updated in the last 24 hours.

## PARAMETERS

### -Identifier
Specifies an array of unique identifiers of the relying party trust to get.

```yaml
Type: String[]
Parameter Sets: Identifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the display name of the relying party trust to get.

```yaml
Type: String[]
Parameter Sets: RelyingPartyName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PrefixIdentifier
Specifies a prefix identifier of the relying party trust to get.
The Federation Service uses prefix matching to support wildcard-type filtering and perform matches based on a specific prefix URL.
The Federation Service performs matches by using string data type evaluation.
Matches are not case-sensitive.

```yaml
Type: String
Parameter Sets: PrefixIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

String objects are received by the *Identifier*, *Name*, and *PrefixIdentifier* parameters.

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.RelyingPartyTrust

Returns one or more RelyingPartyTrust objects that represent the relying party trust resources for the Federation Service.

## NOTES
* If no *Identifier* parameter is provided, the cmdlet returns all **RelyingPartyTrust** objects. A relying party in Active Directory Federation Services (AD FS) is an organization in which Web servers that host one or more Web-based applications reside. Tokens and Information Cards that originate from a claims provider can then be presented and ultimately consumed by the Web-based resources that are located in the relying party organization. When AD FS is configured in the role of the relying party, it acts as a partner that trusts a claims provider to authenticate users. Therefore, the relying party consumes the claims that are packaged in security tokens that come from users in the claims provider. In other words, a relying party is the organization whose Web servers are protected by the resource-side federation server. The federation server at the relying party uses the security tokens that the claims provider produces to issue tokens to the Web servers that are located in the relying party.

## RELATED LINKS

[Add-AdfsRelyingPartyTrust](./Add-AdfsRelyingPartyTrust.md)

[Disable-AdfsRelyingPartyTrust](./Disable-AdfsRelyingPartyTrust.md)

[Enable-AdfsRelyingPartyTrust](./Enable-AdfsRelyingPartyTrust.md)

[Remove-AdfsRelyingPartyTrust](./Remove-AdfsRelyingPartyTrust.md)

[Set-AdfsRelyingPartyTrust](./Set-AdfsRelyingPartyTrust.md)

[Update-AdfsRelyingPartyTrust](./Update-AdfsRelyingPartyTrust.md)

