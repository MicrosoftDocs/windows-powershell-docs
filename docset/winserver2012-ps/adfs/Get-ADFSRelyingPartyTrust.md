---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsrelyingpartytrust?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADFSRelyingPartyTrust

## SYNOPSIS
Gets the relying party trusts of the Federation Service.

## SYNTAX

### RelyingPartyName (Default)
```
Get-ADFSRelyingPartyTrust [[-Name] <String[]>] [<CommonParameters>]
```

### Identifier
```
Get-ADFSRelyingPartyTrust [-Identifier] <String[]> [<CommonParameters>]
```

### PrefixIdentifier
```
Get-ADFSRelyingPartyTrust [-PrefixIdentifier] <String> [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFSRelyingPartyTrust cmdlet retrieves the relying party trusts in the Federation Service.
You can use this cmdlet with no parameters to get all relying party trust objects.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADFSRelyingPartyTrust -Name SampleApp
```

Description

-----------

Gets the current property settings for a relying party trust that is specified by name SampleApp.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADFSRelyingPartyTrust -Identifier https://www.fabrikam.com/
```

Description

-----------

Gets the current property settings for a relying party trust that is specified by the identifier `https://www.fabrikam.com`.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADFSRelyingPartyTrust | Where-Object{ $_.LastUpdateTime  -le  (get-date).subtract((new-timespan -hours 24))}
```

Description

-----------

Gets the current property settings for any relying party trusts that have been updated within the last 24 hours.

## PARAMETERS

### -Identifier
Specifies the unique identifier of the relying party trust to retrieve.

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
Specifies the display name of the relying party trust to retrieve.

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
Specifies a prefix identifier of the relying party trust to retrieve. 
Prefix matching is used to support wildcard-type filtering and do matches based on a specific prefix URL.
Matches are done using string data type evaluation and are not case-sensitive.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.RelyingPartyTrust
A class structure that represents a relying party trust.

## NOTES
* If no Target* parameter is provided, all RelyingParty objects are returned. A relying party in Active Directory Federation Services (AD FS) 2.0 is an organization in which Web servers that host one or more Web-based applications reside. Tokens and Information Cards that originate from a claims provider can then be presented and ultimately consumed by the Web-based resources that are located in the relying party organization. When AD FS 2.0 is configured in the role of the relying party, it acts as a partner that trusts a claims provider to authenticate users. Therefore, the relying party consumes the claims that are packaged in security tokens that come from users in the claims provider. In other words, a relying party is the organization whose Web servers are protected by the resource-side federation server. The federation server at the relying party uses the security tokens that the claims provider produces to issue tokens to the Web servers that are located in the relying party.

## RELATED LINKS

[Add-ADFSRelyingPartyTrust](./Add-ADFSRelyingPartyTrust.md)

[Disable-ADFSRelyingPartyTrust](./Disable-ADFSRelyingPartyTrust.md)

[Enable-ADFSRelyingPartyTrust](./Enable-ADFSRelyingPartyTrust.md)

[Remove-ADFSRelyingPartyTrust](./Remove-ADFSRelyingPartyTrust.md)

[Set-ADFSRelyingPartyTrust](./Set-ADFSRelyingPartyTrust.md)

[Update-ADFSRelyingPartyTrust](./Update-ADFSRelyingPartyTrust.md)

