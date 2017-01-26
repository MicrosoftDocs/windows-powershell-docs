---
author: brianlic-msft
description: 
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Set-WsusProduct
ms.assetid: 7C1A016A-A56E-44A2-9046-005490F13D82
---

# Set-WsusProduct

## SYNOPSIS
Sets whether the product representing the category of updates to synchronize is enabled.

## SYNTAX

```
Set-WsusProduct -Product <WsusProduct> [-Disable] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WsusProduct** cmdlet enables or disables the product representing the category of updates to synchronize.
In order to use this cmdlet, the [Get-WsusProduct](./Get-WsusProduct.md) cmdlet must be run with its results passed into this cmdlet.
You can run the [Where-Object](http://go.microsoft.com/fwlink/?LinkID=113423) cmdlet to filter results.

## EXAMPLES

### Example 1: Specify updates for a product
```
PS C:\> Get-WsusServer | Get-WsusProduct | Where-Object -FilterScript {$_.product.title -Eq "Antigen"} | Set-WsusProduct
```

This command specifies that you want updates for the Antigen product.

## PARAMETERS

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

### -Disable
Specifies that updates are not to be synchronized for the specified product.

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

### -Product
Specifies the product for which the updates are to be synchronized.
If the **Disable** parameter is used, then this parameter specifies the product for which the updates are not to be synchronized.
This parameter value is passed from the [Get-WsusProduct](./Get-WsusProduct.md) cmdlet.

```yaml
Type: WsusProduct
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Where-Object](http://go.microsoft.com/fwlink/p/?LinkID=289623)

[Get-WsusProduct](./Get-WsusProduct.md)

[Get-WsusServer](./Get-WsusServer.md)
