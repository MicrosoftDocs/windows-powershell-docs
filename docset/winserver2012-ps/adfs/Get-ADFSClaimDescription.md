---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: B509236C-E311-4683-9DA2-A403BE87D914
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-ADFSClaimDescription

## SYNOPSIS
Gets claim descriptions that are in the Federation Service.

## SYNTAX

### Name (Default)
```
Get-ADFSClaimDescription [[-Name] <String[]>] [<CommonParameters>]
```

### Identifier
```
Get-ADFSClaimDescription -ClaimType <String[]> [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFSClaimDescription cmdlet retrieves the claim descriptions that are in the Federation Service.
Claim descriptions describe the claims that the Federation Service uses.
They also describe how these claims are published in federation metadata.
You can use this cmdlet without parameters to get the full list of claim descriptions.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADFSClaimDescription | Where -Object {$_.IsOffered}
```

Description

-----------

Gets the list of claim descriptions that the Federation Service offers.

## PARAMETERS

### -ClaimType
Specifies the claim type of the claim description to retrieve.

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
Specifies the name of the claim description to retrieve.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimDescription
A class structure that represents the claim description resources for the Federation Service.

## NOTES
* Claim descriptions are used to configure the list of claims available to be offered or accepted by AD FS 2.0.

## RELATED LINKS

[Add-ADFSClaimDescription](./Add-ADFSClaimDescription.md)

[Remove-ADFSClaimDescription](./Remove-ADFSClaimDescription.md)

[Set-ADFSClaimDescription](./Set-ADFSClaimDescription.md)

