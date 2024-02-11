---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsclaimdescription?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsClaimDescription
---

# Get-AdfsClaimDescription

## SYNOPSIS
Gets claim descriptions from the Federation Service.

## SYNTAX

### Name (Default)
```
Get-AdfsClaimDescription [[-Name] <String[]>] [<CommonParameters>]
```

### Identifier
```
Get-AdfsClaimDescription -ClaimType <String[]> [<CommonParameters>]
```

### ShortName
```
Get-AdfsClaimDescription -ShortName <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsClaimDescription** cmdlet gets claim descriptions from the Federation Service.
Claim descriptions describe the claims that the Federation Service uses.
Claim descriptions also describe how claims are published in federation metadata.
You can use this cmdlet without parameters to get all claim descriptions in the Federation Service.

## EXAMPLES

### Example 1: Get a claim description
```powershell
PS C:\> Get-AdfsClaimDescription | Where-Object {$_.IsOffered}
```

This command gets the list of claim descriptions that the Federation Service offers.

## PARAMETERS

### -ClaimType
Specifies an array of claim type URNs or URIs of the claim.
The cmdlet gets the claim descriptions for the claims that you specify.

```yaml
Type: String[]
Parameter Sets: Identifier
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of claim descriptions to get.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ShortName
Specifies the unique short name ID for the claim description that is used for issuing and consuming JWT tokens.

```yaml
Type: String[]
Parameter Sets: ShortName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

String objects are received by the *ClaimType*, *Name*, and *ShortName* parameters.

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimDescription

Returns one or more ClaimDescription objects that represent the claim description resources for the Federation Service.

## NOTES
* Use claim descriptions to configure the list of claims available to be offered or accepted by Active Directory Federation Services (AD FS).

## RELATED LINKS

[Add-AdfsClaimDescription](./Add-AdfsClaimDescription.md)

[Remove-AdfsClaimDescription](./Remove-AdfsClaimDescription.md)

[Set-AdfsClaimDescription](./Set-AdfsClaimDescription.md)
