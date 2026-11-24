---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/updateservices/get-wsusproduct?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WsusProduct
---

# Get-WsusProduct

## SYNOPSIS

Gets the list of all products currently available on WSUS.

## SYNTAX

```powershell
Get-WsusProduct [-UpdateServer <IUpdateServer>] [-TitleIncludes <String>] [<CommonParameters>]
```

## DESCRIPTION

The **Get-WsusProduct** cmdlet gets the list of all Windows Server Update Services (WSUS) products (categories).

This list can be filtered using the [Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423) cmdlet with the results passed into the [Set-WsusProduct](./Set-WsusProduct.md) cmdlet.

## EXAMPLES

### Example 1: Get all products for a WSUS server

```text
PS C:\> Get-WsusProduct
Title                                                       ID
-----                                                       --
Antigen for Exchange/SMTP                                   5d6a452a-55ba-4e11-adac-85e180bda3d6
Antigen                                                     116a3557-3847-4858-9f03-38e94b977456
```

This command gets all products defined by the WSUS server.

### Example 2: Get products by title

```text
PS C:\> Get-WsusProduct | Where-Object -FilterScript {$_.product.title -eq "Antigen"}
Title                                                       ID
-----                                                       --
Antigen                                                     116a3557-3847-4858-9f03-38e94b977456
```

This command gets all products where the product title is equal to Antigen.

### Example 3: Get products by partial title

```text
PS C:\> Get-WsusProduct | Where-Object -FilterScript {$_.product.title -match "Office"}
Title                                                       ID
-----                                                       --
Office 2002/XP                                              6248b8b1-ffeb-dbd9-887a-2acf53b09dfe
Office 2003                                                 1403f223-a63f-f572-82ba-c92391218055
Office 2007                                                 041e4f9f-3a3d-4f58-8b2f-5e6fe95c4591
Office 2010                                                 84f5f325-30d7-41c4-81d1-87a0e6535b66
Office Communications Server 2007 R2                        22bf57a8-4fe1-425f-bdaa-32b4f655284b
Office Communications Server 2007                           e164fc3d-96be-4811-8ad5-ebe692be33dd
Office Communications Server And Office Communicator        504ae250-57c5-484a-8a10-a2c35ea0689b
Office Communicator 2007 R2                                 8bc19572-a4b6-4910-b70d-716fecffc1eb
Office                                                      477b856e-65c4-4473-b621-a8b230bb70d9
Visual Studio 2010 Tools for Office Runtime                 cbfd1e71-9d9e-457e-a8c5-500c47cfe9f3
```

This command gets all products where the product title contains the word Office.

## PARAMETERS

### -TitleIncludes

Specifies the partial title of the product for which to search.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer

Specifies the object that contains the WSUS server. This value is obtained by calling the Get-WsusServer cmdlet and passing the resulting **IUpdateServer** object into this cmdlet.

```yaml
Type: IUpdateServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.UpdateServices.Administration.IUpdateServer

## OUTPUTS

### Microsoft.UpdateServices.Commands.WsusProduct

## NOTES

## RELATED LINKS

[Where-Object](https://go.microsoft.com/fwlink/?LinkID=113423)

[Set-WsusProduct](./Set-WsusProduct.md)
