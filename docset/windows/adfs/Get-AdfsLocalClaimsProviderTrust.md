---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: ADFS
ms.assetid: 7189AFEF-9CDC-4865-BC8A-1DB7572B7D11
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-AdfsLocalClaimsProviderTrust
ms.reviewer:
---

# Get-AdfsLocalClaimsProviderTrust

## SYNOPSIS
Gets local claims provider trusts.

## SYNTAX

### ClaimsProviderName (Default)
```
Get-AdfsLocalClaimsProviderTrust [[-Name] <String[]>] [<CommonParameters>]
```

### Identifier
```
Get-AdfsLocalClaimsProviderTrust [-Identifier] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsLocalClaimsProviderTrust** cmdlet gets local claims provider trusts.
Specify names or IDs of trusts to get.

## EXAMPLES

## PARAMETERS

### -Identifier
Specifies an array of IDs of the local claims provider trusts to get.

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
Specifies an array of names of the local claims provider trusts to get.

```yaml
Type: String[]
Parameter Sets: ClaimsProviderName
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AdfsLocalClaimsProviderTrust](./Add-AdfsLocalClaimsProviderTrust.md)

[Disable-AdfsLocalClaimsProviderTrust](./Disable-AdfsLocalClaimsProviderTrust.md)

[Enable-AdfsLocalClaimsProviderTrust](./Enable-AdfsLocalClaimsProviderTrust.md)

[Remove-AdfsLocalClaimsProviderTrust](./Remove-AdfsLocalClaimsProviderTrust.md)

[Set-AdfsLocalClaimsProviderTrust](./Set-AdfsLocalClaimsProviderTrust.md)

